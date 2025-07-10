# Broken Access Control
 Uma vulnerabilidade que permite um usuário consiga visualizar, modificar e apagar dados ou informações. 

# Observações
Pode ser confudido com IDOR, mas existe diferença! Se o usuário não está autenticado e consegue acessar as páginas e se um não admininistrador pode acessar a página de admiinistração. Amabse são vulneraveis a Broken Access Control

# Extras
**_A autenticação_**: confirma que o usuário é quem diz ser.

**_Gerenciamento de sessão_**: Identifica quais solicitações HTTP estão sendo feitas pelo mesmo usuário

**_Controle de sessão_**: Determina se o usuário tem permissão para a realizar uma ação que está tentando executar.

Escalação de privilégios
- Vertical: Usuários com diferentes privilégios
- Horizontal: Usuários com mesmos privilégios

# Correções
- Realizar as validações do lado do servidor
- Política de menor privilégio

