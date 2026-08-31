# Desafio: Contribuintes OO e Lista

Aplicação de console em Java que calcula o imposto de renda de N contribuintes, armazenando os dados em uma `List<TaxPayer>` e exibindo um resumo individual do imposto bruto, abatimento e imposto devido.

Desafio do capítulo "Memória, vetores, listas" do módulo Programação Moderna da Formação Desenvolvedor Moderno ([DevSuperior](https://devsuperior.com.br)).

## Regras de negócio

**1. Imposto sobre salário**, conforme o salário mensal:

| Salário mensal | Imposto |
|---|---|
| Abaixo de 3000 | Isento |
| De 3000 até 5000 (exclusive) | 10% |
| 5000 ou acima | 20% |

**2. Renda com prestação de serviços:** imposto de 15%.

**3. Ganho de capital** (imóveis, ações, etc.): imposto de 20%.

**4. Abatimento:** a pessoa pode abater até 30% do imposto bruto devido com gastos médicos ou educacionais. Se a soma desses gastos for menor que 30% do imposto bruto, abate-se apenas o valor dos gastos.

## Modelo de domínio

```
TaxPayer
- salaryIncome : double
- servicesIncome : double
- capitalIncome : double
- healthSpending : double
- educationSpending : double

+ salaryTax() : double
+ servicesTax() : double
+ capitalTax() : double
+ grossTax() : double
+ taxRebate() : double
+ netTax() : double
```

## Estrutura do projeto

```
src/
├── application/
│   └── Program.java     # leitura dos dados e exibição dos resumos
└── entities/
    └── TaxPayer.java    # atributos encapsulados e regras de cálculo
```

## Exemplo de execução

```
Quantos contribuintes você vai digitar? 2

Digite os dados do 1o contribuinte:
Renda anual com salário: 48000.00
Renda anual com prestação de serviço: 0.00
Renda anual com ganho de capital: 800.00
Gastos médicos: 400.00
Gastos educacionais: 5400.00

Digite os dados do 2o contribuinte:
Renda anual com salário: 189000.00
Renda anual com prestação de serviço: 55184.93
Renda anual com ganho de capital: 20000.00
Gastos médicos: 600.00
Gastos educacionais: 7500.00

Resumo do 1o contribuinte:
Imposto bruto total: 4960.00
Abatimento: 1488.00
Imposto devido: 3472.00

Resumo do 2o contribuinte:
Imposto bruto total: 50077.74
Abatimento: 8100.00
Imposto devido: 41977.74
```

## Como executar

Pré-requisito: JDK 8 ou superior (desenvolvido e testado no JDK 21).

```bash
git clone https://github.com/iagoclima22/desafio-contribuintes-oo-lista.git
cd desafio-contribuintes-oo-lista/src
javac application/Program.java entities/TaxPayer.java
java application.Program
```

Os valores devem ser digitados com ponto como separador decimal, já que a aplicação define `Locale.US`.

## Conceitos praticados

- Classes, atributos privados e encapsulamento com get/set
- Construtores sobrecarregados
- Métodos de negócio na própria entidade
- Coleções: `List` e `ArrayList`
- Formatação de saída com `printf` e `Locale`

## Autor

Iago Lima

GitHub · [iagoclima22](https://github.com/iagoclima22)
