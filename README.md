# JAVA E SPRING SECURITY: proteja suas aplicações web

## Esse curso é separado em 5 módulos:

### Índice
- [Módulo 1: Utilizando a proteção automática do Spring Security](#Módulo-1:-Utilizando-a-proteção-automática-do-Spring-Security)
- [Módulo 2: Personalizando as configurações de segurança](#Módulo-2:-Personalizando-as-configurações-de-segurança)
- [Módulo 3: Gerenciando sessões](#Módulo-3:-Gerenciando-sessões)
- [Módulo 4: Autenticação com OAuth2](#Módulo-4:Persistindo-usuários-no-banco-de-dados)
- [Módulo 5: Autenticação com JWT](#Módulo-5:-Integrando-o-Thymeleaf-ao-Spring-SecurityIntegrando-o-Thymeleaf-ao-Spring-Security)

1. ## **Módulo 1: Utilizando a proteção automática do Spring Security
- Adicionar o Spring Security em uma aplicação web com Spring Boot, utilizando a dependência do Spring Security no pom.xml.

- Sobrescrever o comportamento padrão de segurança com uma classe de configuração. Para isso, criamos uma classe de configuração de segurança com @Configuration e @EnableWebSecurity, onde é possível personalizar nossa camada de segurança.

- Personalizar as configurações de segurança com múltiplos beans. Entendemos que, para trocar as configurações padrão do Spring, utilizamos os beans, onde dizemos ao framework que determinado objeto deverá ser gerenciado por ele.

- Criar usuários específicos para a aplicação. Fizemos isso sobrescrevendo o bean de UserDetailsService.

- Utilizar prefixo "{noop}" durante o desenvolvimento. Vimos que esse prefixo é muito útil quando não queremos configurar um PasswordEncoder para as senhas.


2. ## ** Módulo 2: Personalizando as configurações de segurança
- A importância de criar páginas de login e logout personalizadas para manter a consistência visual do aplicativo. Isso está muito relacionado à experiência do usuário: é interessante uma consistência no visual das páginas e no idioma utilizado por elas.

- Como alterar as configurações padrão de filtro do Spring Security. Fizemos isso criando um bean do tipo SecurityFilterChain, o que permite que tenhamos nossa própria cadeia de filtros.

- Configurações relacionadas às requisições HTTP. Ao utilizarmos nosso próprio filtro, precisamos adicionar a configuração das requisições, inserindo arquivos front-end, para evitar que o aplicativo quebre.

- Como o Spring Security lida com logout. Vimos que o LogoutFilter requer uma rota POST para /logout para fazer todas as limpezas necessárias.

3. ## ** Módulo 3: Gerenciando sessões
- O fluxo entre login e logout. Quando fazemos login, criamos uma sessão, e quando fazemos logout, precisamos limpá-la.

- A trabalhar com sessões e cookies. Vimos que as informações precisam ser guardadas tanto do lado do navegador, com os cookies, quanto do lado do servidor, com a sessão. A aplicação sempre verifica o JSESSIONID enviado pelo navegador para permitir ou não que um usuário acesse as páginas do site.

- O que é o ataque hijacking e como se proteger dele. Os cookies de sessão são gigantescos, evitando que uma pessoa consiga descobri-los aleatoriamente.

- Como implementar a funcionalidade "Remember Me" no Spring Security. Podemos criar um filtro adicional, que cuidará da criação de um cookie chamado Remember Me no navegador. Esse cookie pode ter a duração que acharmos mais apropriada.

- A proteção contra CSRF e a geração de tokens de segurança. Compreendemos como funciona o ataque CSRF e como nos protegemos dele, utilizando os tokens de segurança. Também aprendemos como customizar o CsrfRepository no Spring Security, a fim de trocar a forma como os tokens são gerenciados.

4. ## ** Módulo 4: Persistindo usuários no banco de dados
- Que é melhor armazenarmos os dados de usuários em um banco de dados. Dessa forma, o gerenciamento e a escalabilidade se tornam mais fáceis.

- A implementar corretamente as interfaces fornecidas pelo Spring Security. Criamos nossas próprias implementações de UserDetails e UserDetailsService, indicando para o Spring como ele deveria trabalhar.

- A utilizar injeção de dependência no UsuarioService para acessar o repositório. Usamos a anotação @Service para transformar a classe em um bean.

- A necessidade de configurar um PasswordEncoder para criptografar senhas. Criptografamos as senhas dos usuários no banco e adicionamos o BCryptPasswordEncoder para lidar com as senha criptografadas.

5. ## ** Módulo 5: Integrando o Thymeleaf ao Spring Security
- Integrar Thymeleaf e Spring Security. Isso foi feito adicionando a dependência thymeleaf-extras-springsecurity6 no pom.xml e usando o dialeto de segurança do Thymeleaf em arquivos HTML.

- Usar a tag sec:authorize="isAuthenticated()" para controlar a visualização de elementos no template HTML.

- Personalizar a exibição do nome do usuário autenticado no menu com Thymeleaf e Spring Security. Essa personalização é feita com a tag sec:authentication=”principal.nome”.

- Criar métodos de acesso no UserDetails para a correta integração com Spring Security. Entendemos que o principal da tag se refere ao usuário logado com o Spring Security, que é definido por um UserDetails. Logo, para utilizar as propriedades do principal, temos que ter essa propriedade no usuário, e ela deve ser acessível (por exemplo, devemos ter um getNome()).

- Conclusão 11/2025.