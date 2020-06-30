# Medication Dispense

Projeto para listar os aplicativos de dispensação de medicamentos do Brasil e seus respectivos padrões de identificadores de prescrição.

## Como utilizar

- Inclua o repositório no gerenciador de dependências do seu projeto
- Consuma o arquivo [applications.json](applications.json), o qual contém a lista de aplicativos e seus padrões

## Exemplos

- [Página de exemplo](https://e-prescription-brazil.github.io/medication-dispense-example/), a qual redireciona para o dispensador correto com base no padrão do identificador digitado.

## JSON Schema

O arquivo [applications.json](applications.json) segue as regras definidas em [applications.schema.json](applications.schema.json).

|   |Type|Description|Required|
|---|----|-----------|--------|
|**version**|`string`|A versão do JSON.|:white_check_mark:|
|**applications**|`array`|Lista de aplicativos.|:white_check_mark:|
|**applications[].name**|`string`|Nome do aplicativo.|:white_check_mark:|
|**applications[].homepageUrl**|`string`|URL do site do aplicativo.|:white_check_mark:|
|**applications[].logoUrl**|`string`|URL do logo do aplicativo. Preferencialmente, estará no tamanho 50x50.|:white_check_mark:|
|**applications[].prescription.identifiers**|`array`|Lista de padrões de identificadores de prescrição.|:white_check_mark:|
|**applications[].prescription.identifiers[].char.type**|`string`|Tipo de caracter aceito pelo padrão (alphanumeric, numeric, alphabetic).|:white_check_mark:|
|**applications[].prescription.identifiers[].char.valid**|`string`|String com os caracteres válidos para o padrão.||
|**applications[].prescription.identifiers[].length.min**|`number`|Número mínimo de caracteres do identificador.|:white_check_mark:|
|**applications[].prescription.identifiers[].length.max**|`number`|Número máximo de caracteres do identificador.|:white_check_mark:|
|**applications[].prescription.identifiers[].prefix**|`string`|Prefixo do identificador.||
|**applications[].dispense.homepageUrl**|`string`|URL do site de dispensação de medicamentos.|:white_check_mark:|
|**applications[].dispense.prescriptionUrl**|`string`|URL da página de dispensação de uma prescrição. Deve conter o coringa $PRESCRIPTION_IDENTIFIER, que será substituido pelo identificador da prescrição|:white_check_mark:|


## Origem do redicionamento

Algumas URLs presentes no JSON terão em sua query string o parâmetro *utm_source*, que ajudará os responsáveis dos aplicativos a identificarem a origem do tráfego e possibilitará futuras customizações.

O valor do parâmetro *utm_source* deve ser o slug de sua aplicação. Leva-se em conta o padrão de variáveis [Urchin Tracking Module](https://en.wikipedia.org/wiki/UTM_parameters).

Exemplo: `https://memed.com.br/receita/MD123456?utm_source=nexodata`

## Prefixos

Como forma de facilitar a padronização dos identificadores de prescrição, esse projeto, apesar de aceitar qualquer padrão, propõe o uso de prefixos de 2 letras. Abaixo, uma lista dos prefixos já reservados.

|Empresa|Prefixo|
|---|----|
|Memed|MD|
|Nexodata|NX|
|Doutor Prescreve|DP|

> Quer reservar um prefixo para sua empresa? Abra um PR modificando a tabela acima.

## Contribuindo

Todas as empresas que desenvolvem soluções para a dispensação de medicamentos no Brasil são bem vindas para contribuir com esse projeto.

Por favor, leia o arquivo [CONTRIBUTING.md](CONTRIBUTING.md) para detalhes sobre o processo de submissão de alterações.

## Versionamento

Esse projeto utiliza o [SemVer](http://semver.org/) para versionamento. Para visualizar as versões disponíveis, consulte as [tags desse repositório](https://github.com/e-prescription-brazil/medication-dispense/tags). 

## Mantenedores

* [**Memed**](https://memed.com.br)
* [**Nexodata**](https://nexodata.com.br)

Veja também a lista de [contribuidores](https://github.com/e-prescription-brazil/medication-dispense/contributors) que participaram desse projeto.

## Licença

MIT License - veja em [LICENSE.md](LICENSE.md)
