# Funcionamento do Sistema de Locadora de Veículos com PHP e Bootstrap


Esse documento descreve o funcionamento do sistema de locadora de veículos desenvolvido em PHP, utilizando o Bootstrap para a interface, com autenticação de usuários, gerenciamento de veículos (carros e motos) e persistência de dados em arquivos JSON. O foco principal é explicar o funcionamento geral do sistema, com ênfase especial nos perfis de acesso (admin e usuário).


## 1. Visão Geral do Sistema

O sistema de locadora de veículos é uma aplicação web que permite:

- Autenticação de usuário com dois perfis: **admin** (administraodr) e **usuário**;
- Gerenciamento de veículos: cadastro, aluguel, devolução e exclusão;
- Cálculo de previsão de aluguel: com base no tipo de veículo (carro ou moto) e número de dias;
- Interface responsiva.

Os dados são armazenados em dois arquivos JSON:

- `usuarios.json`: username, senha criptografada e perfil;
- `veiculos.json`: tipo, modelo, placa e status de disponibilidade.


## 2. Estrutura do Sistema
O sistema utiliza:
- **PHP**: para a lógica;
- **Bootstrap**: para a estilização;
- **Bootstrap Icons**: para os ícones da interface;
- **Composer**: para autoloading de classes;
- **JSON**:para persistência de dados.



### 2.1 Componentes principais
- **Interfaces**: Define a interface `Locavel` para veículos e utiliza os métodos `alugar()`, `devolver()` e `isDisponivel()`.
- **Models**: Classes `Veiculos` (abstrata), `Carro` e `Moto` para os veículos, com cálculo de aluguel baseado em diárias constantes (`DIARIA_CARRO` e `DIARIA_MOTO`).
- **Services**: Classes `AUTH` (autenticação e gerenciamento de usuários) e `Locadora` (gerenciamento de veículos).