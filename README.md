# ASKA BBS (Mojolicious�o�[�W����)

����́A�g���₷���f���ł���[Kent Web��ASKA BBS](http://www.kent-web.com/bbs/aska.html)���A
���_����Perl�̕��@��Mojolicious���g���čĎ����������̂ł��B
([�T���v��](http://www.kent-web.com/bbs/aska/aska.cgi))

���̃v���W�F�N�g�́A
CGI�����_����Perl�ŋL�q�ŋL�q���邱�Ƃ�ڕW�ɂ��āA
�J�n����܂����B

# ����

�@�����͈ȉ��̂悤�ɂȂ��Ă��܂��B

* Web�t���[�����[�NMojolicious���g�����f���̎���
* CGI�Ƒg�ݍ��݂�Web�T�[�o�[�Ŏ��s���\
* cpanm�������I�ɂ͗��p����A�����R�}���h�ŁA�Z�b�g�A�b�v������
* Perl 5.10.1�ȏ�ł��邱�Ƃ������v���B
* ������̃����^���T�[�o�[�E�X�^���_�[�h�œ��������Ƃ��ł��܂��B
  (SuExec��ݒ肵�Ă��鋤�L�����^���T�[�o�[�Ȃ痘�p���\)
  
# Perl�̃o�[�W�����̊m�F

Perl�̃o�[�W�������m�F���Ă��������B5.10.1�ȏ�ł���΁A���p�ł��܂��B

    perl -v

# �_�E�����[�h(�J����)

�ȉ��̗��p���@�ŁA�_�E�����[�h����f�B���N�g�����ς��܂��B

## suEXEC����񋟂��Ă��鋤�L�����^���T�[�o�[��CGI�Ƃ��Đݒu����ꍇ

����͂�����̃����^���T�[�o�[�E�X�^���_�[�h�Ȃǂ��Y�����܂��B
CGI��ݒu����f�B���N�g���Ɉړ����Ă��������B���̏ꏊ�́AOS�ɂ���ĈقȂ�܂��B

    cd ~/www

## �������Ǘ����Ă���T�[�o�[��CGI�Ƃ��Đݒu����ꍇ

root�����ɂȂ�܂��B

    su -

���ɁAWeb�T�[�o�[�̃h�L�������g���[�g�Ɉړ����܂��B���̏ꏊ�́AOS�ɂ���ĈقȂ�܂��B

    cd /var/www/html

���̏ꍇ�́A�h�L�������g���[�g�ɂ�����CGI�����s�ł���ݒ�ɂȂ��Ă���K�v������܂��̂ŁA
�`�F�b�N���Ă��������B

���Ƃ��Έȉ��̐ݒ肪�K�v�ł��B

    <Directory /var/www/html>
        Options +ExecCGI
        AddHandler cgi-script .cgi
    </Directory>

## �������Ǘ����Ă���T�[�o�[�őg�ݍ��݂�Web�T�[�o�[���g���ċN������ꍇ

���[�U�[�����ŁA�D���ȏꏊ�Ƀ_�E�����[�h���Ă��������B���̕��@�́A
�Ǘ��̎�Ԃ������܂����A�p�t�H�[�}���X�ɂ����ėL���ł��B

## �_�E�����[�h���

�_�E�����[�h���܂��B

    curl -kL https://github.com/yuki-kimoto/kent-aska-mojo/archive/devel.tar.gz > aska-devel.tar.gz

�W�J���܂��B

    tar xf aska-devel.tar.gz

���O��ύX���܂��B

    mv kent-aska-mojo-devel aska

# �Z�b�g�A�b�v

�f�B���N�g���̒��Ɉړ����܂��B

    cd aska

ASKA BBS���ŏ��ɃZ�b�g�A�b�v���܂��B�K�v�ȃ��W���[�����C���X�g�[������܂��B

    ./setup.sh

## �������Ǘ����Ă���T�[�o�[��CGI�Ƃ��Đݒu����ꍇ�̒ǉ��̏���

�������Ǘ����Ă���T�[�o�[��CGI�Ƃ��Đݒu����ꍇ�́A�t�@�C���̌�����apache
�����s�ɐ؂�ւ��܂��B���̒l�́AApache�̐ݒ����ĈقȂ�ꍇ������܂��B

    cd /var/www/html
    chown -R apache:apache aska

# ASKA BBS�ւ̃A�N�Z�X

## suEXEC����񋟂��Ă��鋤�L�����^���T�[�o�[��CGI�Ƃ��Đݒu����ꍇ

Web�u���E�U����uaska.cgi�v�ɃA�N�Z�X���Ă��������B

    http://yourhost/aska/aska.cgi
    
## �������Ǘ����Ă���T�[�o�[�őg�ݍ��݂�Web�T�[�o�[���g���ċN������ꍇ

Web�u���E�U����uaska.cgi�v�ɃA�N�Z�X���Ă��������B

    http://yourhost/aska/aska.cgi

## �������Ǘ����Ă���T�[�o�[�őg�ݍ��݂�Web�T�[�o�[���g���ċN������ꍇ

�A�v���P�[�V�������J�n����ɂ͎��̂悤�ɂ��܂��B

    ./aska

�|�[�g�ԍ���10080�ŋN������̂ŁAURL�ŃA�N�Z�X���Ă��������B

    http://yourhost:10080

�A�v���P�[�V�������~����ɂ͎��̂悤�ɂ��܂��B

    ./aska --stop

# ASKA BBS����̈ڍs���@

�f�[�^�t�@�C��(log/log.cgi)���R�s�[���āA�udata/data.txt�v��UTF-8�ŕۑ����Ă��������B

# �ݒ�t�@�C��

�ݒ�t�@�C���́uaska.conf�v�ł��B�n�b�V���̃��t�@�����X�ŋL�q����Ă��܂��B

# FAQ

## PSGI�ɑΉ����Ă��܂���

�͂�PSGI�ɑΉ����Ă��܂��B

## Perl�̃o�[�W������5.8�ł�

���̂悤�ȏꍇ�́Aperlbrew���g���āA5.10.1�ȏ��Perl���C���X�g�[�����邱�ƂŁA
���p���邱�Ƃ��\�ɂȂ�܂��BCGI�͖����ł����A�g�ݍ��݂�Web�T�[�o�[���g����
���p�ł��܂��B

## Image::Magick���C���X�g�[������Ă��邩�̊m�F�������ł�

Image::Magick���C���X�g�[������Ă��邩�ǂ������m�F����ɂ́A
�ȉ��̃R�}���h�Ŋm�F�ł��܂��B

    perldoc Image::Magick
