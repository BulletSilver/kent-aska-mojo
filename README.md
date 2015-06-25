# ASKA BBS (Mojolicious�o�[�W����)

����́A�g���₷���f���ł���[Kent Web��ASKA BBS](http://www.kent-web.com/bbs/aska.html)���A
���_����Perl�̕��@��Mojolicious���g���čĎ����������̂ł��B
([�T���v��](http://www.kent-web.com/bbs/aska/aska.cgi))

���̃v���W�F�N�g�́A
CGI�����_����Perl�ŋL�q�ŋL�q���邱�Ƃ�ڕW�ɂ��āA
�J�n����܂����B

## ����

�@�����͈ȉ��̂悤�ɂȂ��Ă��܂��B

- Web�t���[�����[�NMojolicious���g�����f���̎���
- cpanm�������I�ɂ͗��p����A�����R�}���h�ŁA�Z�b�g�A�b�v������
- Perl 5.10.1�ȏ�ł��邱�Ƃ������v���B
- CGI�Ƒg�ݍ��݂�Web�T�[�o�[�Ŏ��s���\
- ���Ƃ��΁A������̃����^���T�[�o�[�E�X�^���_�[�h�œ��������Ƃ��ł��܂��B

## Perl�̃o�[�W�����̊m�F

Perl�̃o�[�W�������m�F���Ă��������B5.10.1�ȏ�ł���΁A���p�ł��܂��B

    perl -v

## A. CGI�Ƃ��ė��p����ꍇ�̃C���X�g�[�����@

CGI��ݒu�������f�B���N�g���ɁA�_�E�����[�h���Ă��������B

    curl -kL https://github.com/yuki-kimoto/kent-aska-mojo/archive/latest.tar.gz > aska-latest.tar.gz

�W�J���܂��B

    tar xf aska-latest.tar.gz

���O��ύX���܂��B

    mv kent-aska-mojo-latest aska

�f�B���N�g���̒��Ɉړ����܂��B

    cd aska

�Z�b�g�A�b�v���܂��B�K�v�ȃ��W���[�����C���X�g�[������܂��B

    ./setup.sh

�Z�b�g�A�b�v�̊m�F�����܂��B�ȉ��̃R�}���h�����s���Ă��������B

    perl -c aska.pl

�Ɠ��͂��Ă��������B�usyntax OK�v�ƕ\�������΃Z�b�g�A�b�v���������Ă��܂��B

CGI��ݒu�����玟��URL�ŃA�N�Z�X���邱�Ƃ��ł��܂��B

    http://yourhost/somepath/aska/aska.cgi

��L�̕��@�́A������̃X�^���_�[�h�ŗ��p�ł��邱�Ƃ��m�F�ς݂ł��B

### �����̃��[�U�[�����Ŏ������Ȃ��ꍇ�̒ǉ��̍��

�@CGI�X�N���v�g���A�����̃��[�U�[�����Ŏ����ł��Ȃ����̏ꍇ�́A���̒ǉ��̍�Ƃ��s���Ă��������B
���Ƃ��΁ACGI�X�N���v�g��apache�����Ŏ��s�����悤�ȏꍇ�ł��B

aska�f�B���N�g���̒��̂��ׂẴt�@�C����apache���[�U�[�����ɕύX���܂��B

    chown -R apache:apache aska

�܂��A���̏ꍇ�́ACGI�����s�ł���ݒ�ɂȂ��Ă���K�v������܂��̂ŁA
Apache�̐ݒ�t�@�C�����`�F�b�N���Ă��������B

���Ƃ��Έȉ��̂悤�Ȑݒ肪�K�v�ł��B

    <Directory /var/www/html>
        Options +ExecCGI
        AddHandler cgi-script .cgi
    </Directory>

### B. �g�ݍ��݂̃T�[�o�[�Ŏ�������ꍇ�̃C���X�g�[�����@

�C�ӂ̃f�B���N�g���ɁA�_�E�����[�h���Ă��������B

    curl -kL https://github.com/yuki-kimoto/kent-aska-mojo/archive/latest.tar.gz > aska-latest.tar.gz

�W�J���܂��B

    tar xf aska-latest.tar.gz

���O��ύX���܂��B

    mv kent-aska-mojo-latest aska

�f�B���N�g���̒��Ɉړ����܂��B

    cd aska

�Z�b�g�A�b�v���܂��B�K�v�ȃ��W���[�����C���X�g�[������܂��B

    ./setup.sh

�Z�b�g�A�b�v�̊m�F�����܂��B�ȉ��̃R�}���h�����s���Ă��������B

    perl -c aska.pl

�Ɠ��͂��Ă��������B�usyntax OK�v�ƕ\�������΃Z�b�g�A�b�v���������Ă��܂��B

�g�ݍ��݂̃T�[�o�[���N�����܂��B

    ./aska

�|�[�g�ԍ���10080�ŋN������̂ŁA����URL�ŃA�N�Z�X���Ă��������B

    http://yourhost:10080

�A�v���P�[�V�������~����ɂ͎��̂悤�ɂ��܂��B

    ./aska --stop

## �ݒ�t�@�C��

�ݒ�t�@�C���́uaska.conf�v�ł��B�n�b�V���̃��t�@�����X�ŋL�q����Ă��܂��B

## FAQ

### ASKA BBS����̓����I�ȉ��P�_�������Ă��������B

- Web�t���[�����[�N�Ƃ���Mojolicious�𗘗p�B
  - HTTP���N�G�X�̉�́A�p���[���[�^�̎󂯎��A�N�b�L�[�̎擾����
  - URL�̃��[�e�B���O�̉��P�A�e���v���[�g�̋L�q�����P�A�w�b�_�A�t�b�^�𕔕i��
- �O���[�o���ȃt�@�C���n���h���͗��p�����ɁA���L�V�J���ϐ����g�p
- �K�v���W���[���̃C���X�g�[���̃V�X�e���Ƃ���cpanm���g�p
- Email�̑��M��MIME::Lite���g�p���ĊȌ��ɂ���
- �y�[�W����̏�����Data::Page��Data::Page::Navigation�𗘗p���ĊȌ��ɂ����B
- �����R�[�h�̃G���R�[�h�ɂ�Encode���W���[�����g�p�BJCode�̎g�p���Ȃ������B
- �f�[�^�ۑ��̂Ƃ��̃G���R�[�h�����̃��W�b�N�����ʉ����ĉ��P
- CGI�ɉ����đg�ݍ���Web�T�[�o�[�ŋN�����ł���̂ŁA���ɍ����ŃX�P�[���r���e�B������B
- �J���T�[�o�[�����p�ł���̂ŁA�J�������Ɋy�ɂȂ����B

## ASKA BBS����f�[�^���ڍs���邱�Ƃ͂ł��܂���

�f�[�^�t�@�C��(log/log.cgi)�̓��e���R�s�[���āA�udata/data.txt�v�ɓ\��t���āAUTF-8�ŕۑ����Ă��������B

### CentOS�ŃZ�b�g�A�b�v���ł��܂���

CentOS�ł́APerl�̃R�A���W���[���̂��ׂĂ��C���X�g�[������܂���̂ŁA
�ȉ��̃R�}���h�ŃR�A���W���[�����C���X�g�[�����Ă��������B

    yum -y install perl-core

### PSGI�ɑΉ����Ă��܂���

�͂�PSGI�ɑΉ����Ă��܂��B

### Perl�̃o�[�W������5.8�ł�

���̂悤�ȏꍇ�́Aperlbrew���g���āA5.10.1�ȏ��Perl���C���X�g�[�����邱�ƂŁA
���p���邱�Ƃ��\�ɂȂ�܂��BCGI�͖����ł����A�g�ݍ��݂�Web�T�[�o�[���g����
���p�ł��܂��B

### Image::Magick���C���X�g�[������Ă��邩�̊m�F�������ł�

Image::Magick���C���X�g�[������Ă��邩�ǂ������m�F����ɂ́A
�ȉ��̃R�}���h�Ŋm�F�ł��܂��B

    perldoc Image::Magick

## �J���Ҍ����̏��

�J�����s���ꍇ�́A���̃R�}���h�����s����ƁA�g�ݍ��݂̊J���T�[�o�[���N�����܂��B

    ./morbo

����URL�ŃA�N�Z�X�\�ł��B

    http://yourhost:3000

�uaska.my.conf�v�Ƃ����ݒ�t�@�C�����쐬����ƁA
�����炪�D��I�ɓǂݍ��܂��̂ŕ֗��ł��B

    cp aska.conf aska.my.conf
