# Objetivo do Case
* Desenvolver uma API robusta para gerenciar um sistema de assinaturas de serviços,
contemplando cadastro de usuários, planos, pagamentos e relatórios. O sistema deve
seguir os princípios de clean architecture e aplicar boas práticas de desenvolvimento.

## Cenário de Negócio
* A empresa fictícia "TechSub" fornece assinaturas de software como serviço (SaaS). Seu
time foi designado para desenvolver um módulo completo de gestão de assinaturas,
visando escalabilidade e facilidade de manutenção.

## Requisitos funcionais
1. Usuários e Autenticação
    * Dados básicos, e-mail, autenticação e recuperação de senha.
    * Um usuário pode estar em apenas **uma assinatura ativa por vez**.

2. Planos de Assinatura
    * Planos com preços e recursos distintos (ex: Free, Basic, Pro).
    * Cada plano possui:
        * Nome
        * Preço mensal e anual
        * Elegibilidade para trial

3. Ciclo de Assinatura
    * Ao assinar, o usuário escolhe o plano e a periodicidade (mensal/anual).
    * Suporte a trial de 7 dias, se for o primeiro plano do usuário.
    * Ao fim do trial, cobrança automática se o método de pagamento estiver cadastrado;
    caso contrário, downgrade para Free.
    * Renovação automática no fim do ciclo.

4. Pagamentos
    * Pagamento pode ser apenas simulado.
    * Cobrança recorrente automática.
    * Notificações de pagamento bem-sucedido ou falha.
    * Cancelamento de assinatura com término no fim do ciclo pago.

5. Relatório de Assinaturas
    * Listagem de usuários ativos por plano
    * Receita mensal recorrente (MRR)

## Requisitos não funcionais
1. Arquitetura
    * Clean Architecture / DDD (Domain Driven Design)
    * Camadas bem definidas
    * Injeção de dependência e teste unitário
    * Uso dos conceitos SOLID
2. Tecnologias
    * Backend: C# (.NET Core 8)
    * Banco: PostgreSQL
    * ORM: Entity Framework Core
    * Autenticação: OAuth com JWT
    * Migration para construção do banco de dados
    * Documentação: OpenAPI com Padrão REST