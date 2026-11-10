# Conteúdo dos slides — Trabalho ISO/IEC

**Universidade da Região de Joinville (Univille)**, Sistemas de Informação
**Disciplina:** Fundamentos de Engenharia de Software
**Professor:** Sergio Odilon Fischer
**Integrantes:** Vinícius Pupo Estevom, Thiago Wendt Percyak, Henrique Miguel da Silva, Pedro Luca de Sena e Arthur Voit Reder
Joinville – SC, 2026

> O visual de "boot por CD" é só um trocadilho com a extensão `.iso`. O assunto são as normas ISO/IEC de qualidade de software.

---

## Slide 1 — Capa (tela de BIOS)

A "BIOS" detecta a disciplina, o professor e cada integrante, e avisa que o tema `.iso` é só trocadilho.

**ISO IEC ABNT** — Normas ISO/IEC e qualidade de software

## Slide 2 — Roteiro (menu de boot)

| Imagem | Assunto |
|---|---|
| `siglas.iso` | O que significam ISO, IEC e ABNT |
| `normas.iso` | As normas 14598-5, 12119, 12207, 90003, 15504 e 25000 |
| `square.iso` | Modelos de qualidade: como a ISO/IEC 25000 se organiza |
| `ciclo.iso` | Qualidade no ciclo de vida do software |
| `conceitos.iso` | Qualidade interna, externa e em uso |
| `shutdown` | Síntese, referências e perguntas |

## Slide 3 — Por que tudo aqui termina em .iso?

É um trocadilho. Arquivos de imagem de disco usam a extensão **.iso** porque o CD-ROM segue a norma **ISO 9660**. Por isso cada assunto da apresentação é uma "imagem" que vamos montar.

> O trabalho não é sobre imagens de disco. É sobre as **normas ISO/IEC** que definem como desenvolver, avaliar e medir a **qualidade de software**.

---

## Seção 1 — siglas.iso

### Slide 4 — Abertura

**ISO? IEC? ABNT?** — Quem são as organizações por trás das siglas.

### Slide 5 — ISO

**International Organization for Standardization** (Organização Internacional de Normalização). Elabora normas para praticamente todos os setores: gestão, qualidade, saúde, segurança, tecnologia.

ISO não é uma sigla. Em inglês seria IOS, em francês OIN. O nome vem do grego *ísos*, que significa **igual**: a mesma regra em qualquer país.

| | |
|---|---|
| Fundação | 1947 |
| Sede | Genebra, Suíça |
| Natureza | ONG independente |
| Membros | +170 países (um organismo nacional por país) |
| Exemplo famoso | ISO 9001 |
| Brasil | ABNT |

### Slide 6 — IEC

**International Electrotechnical Commission** (Comissão Eletrotécnica Internacional). Elabora as normas internacionais de tecnologias **elétricas, eletrônicas e relacionadas**. Se tem tomada, bateria ou chip, provavelmente segue uma norma IEC (ex.: o "IP68" do celular vem da IEC 60529).

| | |
|---|---|
| Fundação | 1906, Londres |
| Sede atual | Genebra, Suíça |
| 1º presidente | Lord Kelvin |
| Área | Eletrotécnica |

### Slide 7 — Por que as normas de software são "ISO/IEC"?

Computação é ao mesmo tempo eletrônica (IEC) e informação (ISO). Em **1987** as duas criaram o comitê conjunto **ISO/IEC JTC 1**, de tecnologia da informação. Dentro dele, o subcomitê **SC 7** cuida de engenharia de software e de sistemas.

Todas as normas deste trabalho saíram do JTC 1/SC 7: 14598-5 (avaliação de produto), 12119 (pacotes de software), 12207 (ciclo de vida), 90003 (ISO 9001 para software), 15504 (avaliação de processo) e 25000 (qualidade do produto).

### Slide 8 — ABNT

**Associação Brasileira de Normas Técnicas.** Entidade privada e sem fins lucrativos, reconhecida pelo governo como o **Foro Nacional de Normalização**. Publica as normas brasileiras (**ABNT NBR**) e representa o Brasil na ISO e na IEC. Quando uma norma internacional é adotada aqui, ganha o prefixo ABNT NBR, como a **ABNT NBR ISO/IEC 12207**.

| | |
|---|---|
| Fundação | 1940 |
| Na ISO | membro fundador |
| Normas | ABNT NBR |
| Onde são escritas | Comitês ABNT/CB (empresas, consumidores, governo, universidades) |

### Slide 9 — O nome conta a história da norma

**ISO/IEC 14598-5:1998**

| Parte | Significado |
|---|---|
| `ISO/IEC` | **Origem**: feita em conjunto pela ISO e pela IEC |
| `14598` | **Número**: a série de avaliação de produto de software |
| `-5` | **Parte**: parte 5 da série (processo para avaliadores) |
| `:1998` | **Edição**: ano de publicação |

**ABNT NBR ISO/IEC 12207:2009** é a ISO/IEC 12207 adotada no Brasil: o prefixo mostra o caminho internacional → nacional.

---

## Seção 2 — normas.iso

### Slide 10 — Abertura

**As normas** — O que cada uma descreve e se ainda está em vigor.

### Slide 11 — Seis normas, dois focos

| Norma | Foco | Assunto | Situação |
|---|---|---|---|
| ISO/IEC 14598-5 | produto | Processo de avaliação de produto, para avaliadores | 1998 → hoje ISO/IEC 25040 |
| ISO/IEC 12119 | produto | Pacotes de software: requisitos de qualidade e testes | 1994 → hoje ISO/IEC 25051 |
| ISO/IEC 12207 | processo | Processos do ciclo de vida do software | 1995 → hoje ISO/IEC/IEEE 12207:2017 |
| ISO/IEC 90003 | processo | Como aplicar a ISO 9001 ao software | 2004 → em vigor (2018) |
| ISO/IEC 15504 | processo | Avaliação e melhoria de processos (SPICE) | 1998 → hoje série ISO/IEC 330xx |
| ISO/IEC 25000 | produto | SQuaRE: requisitos e avaliação da qualidade | 2005 → em vigor (2014) |

> As normas de **produto** olham para o software pronto. As de **processo** olham para a forma como ele é feito. Um bom processo aumenta a chance de um bom produto.

### Slide 12 — ISO/IEC 14598-5: processo de avaliação para avaliadores

A série 14598 trata da **avaliação de produto de software** e era usada junto com o modelo de qualidade da ISO/IEC 9126. A **parte 5** orienta quem faz a avaliação (laboratório independente, fornecedor ou comprador). A avaliação deve ser **repetível, reprodutível, imparcial e objetiva**.

As cinco atividades:
1. **Estabelecer os requisitos**: o que avaliar e por quê.
2. **Especificar**: quais características medir e com que critérios.
3. **Projetar**: plano, métodos, recursos e cronograma.
4. **Executar**: medir e comparar com os critérios.
5. **Concluir**: relatório da avaliação para o requerente.

Hoje foi substituída pela ISO/IEC 25040.

### Slide 13 — ISO/IEC 12119: pacotes de software

Trata de **pacotes de software**: produtos prontos, vendidos "de prateleira" (antivírus, editor de texto, sistema de gestão padrão). Define **requisitos de qualidade** e **instruções de teste** para verificar se o pacote cumpre.

| Item | Requisito |
|---|---|
| Descrição do produto | Diz o que o software faz, para o comprador decidir se serve |
| Documentação do usuário | Manual completo, correto e coerente com o produto |
| Programas e dados | O software deve fazer o que a descrição e o manual prometem |

O teste é de conformidade (caixa-preta). Publicada em 1994; substituída pela ISO/IEC 25051.

### Slide 14 — ISO/IEC 12207: processos do ciclo de vida

Cria uma **estrutura comum** de processos, com vocabulário único, para todo o ciclo de vida, da aquisição à retirada. Diz **o que** fazer, não **como**: serve para cascata e para métodos ágeis.

| Grupo (versão de 1995) | Processos |
|---|---|
| Fundamentais | Aquisição, fornecimento, desenvolvimento, operação e manutenção |
| De apoio | Documentação, gerência de configuração, garantia da qualidade, verificação, validação, revisão conjunta, auditoria e resolução de problemas |
| Organizacionais | Gerência, infraestrutura, melhoria e treinamento |

A versão atual (ISO/IEC/IEEE 12207:2017) reorganiza em processos de acordo, organizacionais, de gestão técnica e técnicos. No Brasil: ABNT NBR ISO/IEC 12207.

### Slide 15 — ISO/IEC 90003: a ISO 9001 aplicada ao software

A **ISO 9001** define requisitos de gestão da qualidade para qualquer organização. Software é intangível e não tem "linha de produção", o que dificulta interpretar itens como "controle da produção".

A 90003 é um **guia** que interpreta a ISO 9001, item por item, para quem adquire, fornece, desenvolve, opera e mantém software. Cobre requisitos, projeto, testes, gerência de configuração e manutenção, e se apoia na 12207.

> A empresa é certificada na **ISO 9001**. A 90003 não certifica: ajuda a chegar lá.

### Slide 16 — ISO/IEC 15504: avaliação de processo (SPICE)

*Software Process Improvement and Capability dEtermination.* Avalia os **processos** e mede a **capacidade** de cada um, em duas dimensões: processos (vindos da 12207) e níveis de capacidade. Serve para **melhorar processos** e para **avaliar fornecedores**.

| Nível | Capacidade |
|---|---|
| 0 | Incompleto |
| 1 | Executado |
| 2 | Gerenciado |
| 3 | Estabelecido |
| 4 | Previsível |
| 5 | Em otimização |

No Brasil, é uma das bases do MPS.BR. Hoje foi substituída pela série ISO/IEC 330xx.

### Slide 17 — ISO/IEC 25000: SQuaRE

*Systems and software Quality Requirements and Evaluation.* Nasceu para juntar duas séries que se sobrepunham:

- **ISO/IEC 9126**: modelo de qualidade e métricas do produto
- **ISO/IEC 14598**: processo de avaliação do produto (inclui a 14598-5)

↓ unidas em ↓ **ISO/IEC 25000** (família SQuaRE, 2005, revisada em 2014). A norma 25000 em si é o **guia da família**: organização, termos e como usar as outras normas.

---

## Seção 3 — square.iso

### Slide 18 — Abertura

**Modelos de qualidade** — Como a ISO/IEC 25000 está organizada.

### Slide 19 — Divisões da ISO/IEC 25000

| Divisão | Nome | Conteúdo | Exemplos |
|---|---|---|---|
| 2500n | Gestão da qualidade | Termos, visão geral, planejamento e gestão da avaliação | 25000, 25001 |
| 2501n | Modelo de qualidade | As características de qualidade (centro da família) | 25010, 25012 (dados) |
| 2502n | Medição | Medidas para cada característica | 25022 (em uso), 25023 (produto) |
| 2503n | Requisitos | Como especificar requisitos de qualidade | 25030 |
| 2504n | Avaliação | O processo de avaliar o produto | 25040 (sucessora da 14598-5) |
| 25050 a 25099 | Extensões | Casos específicos | 25051 (sucessora da 12119) |

### Slide 20 — Os modelos de qualidade da ISO/IEC 25010

**Qualidade do produto** (vale para a qualidade interna e a externa):

| Característica | Em poucas palavras |
|---|---|
| Adequação funcional | faz o que precisa fazer |
| Eficiência de desempenho | tempo e recursos |
| Compatibilidade | convive e troca dados com outros |
| Usabilidade | fácil de aprender e usar |
| Confiabilidade | funciona sem falhar |
| Segurança | protege informações |
| Manutenibilidade | fácil de corrigir e mudar |
| Portabilidade | roda em outros ambientes |

**Qualidade em uso** (resultado para o usuário, no contexto real):

| Característica | Em poucas palavras |
|---|---|
| Efetividade | o usuário atinge o objetivo |
| Eficiência | com pouco esforço e tempo |
| Satisfação | e fica satisfeito |
| Ausência de risco | sem dano econômico, à saúde ou ao ambiente |
| Cobertura de contexto | em todos os contextos previstos |

Edição de 2011. A revisão de 2023 renomeou algumas características (usabilidade → capacidade de interação, portabilidade → flexibilidade) e acrescentou *safety*.

---

## Seção 4 — ciclo.iso

### Slide 21 — Abertura

**Ciclo de vida** — Qualidade do primeiro requisito até o fim do uso.

### Slide 22 — Cada fase cuida de uma visão da qualidade

| # | Fase | Visão | O que acontece |
|---|---|---|---|
| 1 | Elicitação de requisitos | em uso | Necessidades do usuário viram requisitos de qualidade em uso, externos e internos (25030) |
| 2 | Projeto e codificação | interna | Revisões e análise do código medem a qualidade interna, sem executar |
| 3 | Testes | externa | O software roda em ambiente de teste: falhas, tempo de resposta |
| 4 | Implantação e operação | em uso | Usuários reais, no contexto real, confirmam se o produto atende |
| 5 | Manutenção | interna | Correções e melhorias voltam ao ciclo; a manutenibilidade pesa aqui |
| 6 | Retirada | processo | Fim do uso: desativação planejada e migração dos dados (12207) |

Em todo o ciclo: a 12207 define os processos; a 15504 e a 90003 avaliam o processo; a 14598-5 / 25040 avaliam o produto.

### Slide 23 — Uma visão de qualidade sustenta a outra

**Processo** → influencia → **Interna** → influencia → **Externa** → influencia → **Em uso**
(e no sentido inverso: cada uma *depende de* a anterior)

> Na especificação o caminho é da direita para a esquerda: o que o usuário precisa define o que o produto deve ter. Na construção é da esquerda para a direita. Qualidade interna boa **não garante** qualidade em uso, mas sem ela é difícil chegar lá.

---

## Seção 5 — conceitos.iso

### Slide 24 — Abertura

**Três visões** — Qualidade interna, externa e em uso.

### Slide 25 — No âmbito da qualidade de software

| | Interna | Externa | Em uso |
|---|---|---|---|
| **Conceito** | Características do produto visto **por dentro**, avaliadas **sem executar** o software (código-fonte, modelos, documentos) | Características do produto visto **por fora**, avaliadas com o software **executando**, em geral em teste e com dados simulados | Quanto o produto, usado por **usuários reais**, permite atingir objetivos com efetividade, eficiência, satisfação e ausência de risco, em **contexto real** |
| **Quando** | Durante o desenvolvimento | Testes de sistema e homologação | Operação |
| **Como** | Revisões, inspeções, análise estática | Testes, simulações | Observação, pesquisas com usuários |
| **Exemplo de medida** | Complexidade do código, duplicação | Falhas por hora de teste, tempo de resposta | % de tarefas concluídas, satisfação |

### Slide 26 — Exemplo: fazer um Pix num app de banco

| Visão | Exemplo |
|---|---|
| Interna | O código do módulo de pagamento passa por revisão, não tem trechos duplicados e tem baixa complexidade |
| Externa | Em teste, a transferência responde em menos de 2 segundos e não falha em mil execuções seguidas |
| Em uso | Um cliente real faz o Pix em menos de 30 segundos, sem errar o valor, e se sente seguro usando o app |

> O app pode passar em todos os testes (externa) e mesmo assim confundir o cliente (em uso). Por isso a avaliação precisa olhar as três visões.

---

## Slide 27 — Resumo

| Seção | Ideia principal |
|---|---|
| siglas | ISO e IEC fazem as normas, juntas no JTC 1; a ABNT as adota no Brasil |
| normas | 14598-5, 12119 e 25000 olham o produto; 12207, 90003 e 15504, o processo |
| square | A 25000 organiza gestão, modelo, medição, requisitos e avaliação |
| ciclo | A qualidade é planejada nos requisitos e verificada até o fim do uso |
| conceitos | Interna → externa → em uso: cada uma sustenta a próxima |

## Slide 28 — Referências e encerramento

- ABNT. Associação Brasileira de Normas Técnicas. Disponível em: https://www.abnt.org.br.
- IEC. International Electrotechnical Commission. Disponível em: https://www.iec.ch.
- ISO. International Organization for Standardization. Disponível em: https://www.iso.org.
- ISO/IEC. ISO/IEC 12119: information technology — software packages — quality requirements and testing. Genebra: ISO, 1994.
- ISO/IEC. ISO/IEC 14598-5: information technology — software product evaluation — part 5: process for evaluators. Genebra: ISO, 1998.
- ISO/IEC. ISO/IEC 15504-2: information technology — process assessment — part 2: performing an assessment. Genebra: ISO, 2003.
- ISO/IEC. ISO/IEC 25000: systems and software engineering — SQuaRE — guide to SQuaRE. Genebra: ISO, 2014.
- ISO/IEC. ISO/IEC 25010: systems and software engineering — SQuaRE — system and software quality models. Genebra: ISO, 2011.
- ISO/IEC. ISO/IEC 90003: software engineering — guidelines for the application of ISO 9001:2015 to computer software. Genebra: ISO, 2018.
- ISO/IEC/IEEE. ISO/IEC/IEEE 12207: systems and software engineering — software life cycle processes. Genebra: ISO, 2017.
- KOSCIANSKI, André; SOARES, Michel dos Santos. Qualidade de software. 2. ed. São Paulo: Novatec, 2007.
- PRESSMAN, Roger S.; MAXIM, Bruce R. Engenharia de software: uma abordagem profissional. 8. ed. Porto Alegre: AMGH, 2016.
- SOMMERVILLE, Ian. Engenharia de software. 10. ed. São Paulo: Pearson, 2019.

> Pendente: acrescentar "Acesso em: dia mês. ano." nas referências de sites (NBR 6023).

`shutdown -h now` — **Obrigado. Perguntas?** Trabalho completo em PDF: `download.html`.
