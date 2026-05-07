### Texto de Apoio: Aula 10 - PPSI-II

## Leitura Complementar Obrigatória: Design Universal e Fundamentos da WCAG

**1. O Paradigma do Design Universal**
Historicamente, a acessibilidade era vista como a criação de "versões alternativas" de um site para pessoas com deficiência. O **Design Universal** quebra esse paradigma: ele defende a concepção de produtos e ambientes que sejam utilizáveis por *todas* as pessoas, na sua máxima extensão possível, sem a necessidade de adaptação ou projeto especializado. Um site com bom contraste não ajuda apenas quem tem baixa visão, ajuda também alguém lendo a tela do celular sob a luz do sol. Uma página navegável por teclado não atende apenas a quem tem limitações motoras, mas também ao usuário avançado (power user) que prefere não usar o mouse.

**2. A Bíblia da Acessibilidade: WCAG 2.0**
A *Web Content Accessibility Guidelines* (WCAG) é o documento oficial do W3C que define como tornar o conteúdo web acessível. Ela é baseada em 4 princípios fundamentais (conhecidos pela sigla **POUR** em inglês ou **PERC** em português):
* **Perceptível:** A informação não pode ser invisível a todos os sentidos do usuário (ex: imagens precisam de texto alternativo para leitores de tela).
* **Operável:** A interface não pode exigir uma interação que o usuário não possa realizar (ex: tudo deve ser navegável via teclado).
* **Compreensível:** A informação e a operação da interface devem ser claras (ex: mensagens de erro explicativas nos formulários).
* **Robusto:** O código deve ser confiável o suficiente para ser interpretado por uma grande variedade de agentes de usuário, incluindo tecnologias assistivas.

**3. Níveis de Conformidade (Prioridade 1)**
A WCAG divide seus critérios de sucesso em três níveis: A (Mínimo/Prioridade 1), AA (Ideal) e AAA (Avançado). No desenvolvimento de qualquer sistema atual, atingir o Nível A (Prioridade 1) é inegociável. Isso inclui garantir que o site não tenha armadilhas de teclado (keyboard traps), que não use apenas a cor para transmitir significado e que toda mídia não-textual tenha uma alternativa em texto.

**4. A Anatomia do Atributo `alt`**
A regra de ouro das imagens:
* **Imagens de Conteúdo:** Trazem informação relevante. O atributo `alt="descrição detalhada"` é obrigatório para que os leitores de tela ditem o que há na imagem.
* **Imagens Decorativas:** Servem apenas para embelezar (ex: um traço separador ou um ícone que já tem o texto escrito do lado). O atributo DEVE estar presente, mas vazio: `alt=""`. Isso instrui o leitor de tela a ignorar a imagem, poupando o tempo do usuário. *Atenção: omitir o atributo alt faz com que o leitor de tela dite o nome do arquivo da imagem (ex: "imagem_traco_azul_v2_final.png"), o que é péssimo para a usabilidade.*

---

## Lista de Exercícios 10: Auditoria e Correção de Interface

Neste laboratório, vocês assumirão o papel de Auditores de Acessibilidade. Vocês receberão uma página que, visualmente, parece "moderna", mas que está cheia de barreiras invisíveis que ferem os princípios da WCAG 2.0 (Nível de Prioridade 1).

**Atividades Práticas:**

1.  **O Desafio do Teclado (Operabilidade):** Abra o arquivo `index.html` no navegador. Esconda o seu mouse. Tente navegar por todos os links e botões da página usando **apenas a tecla TAB** (e Shift+TAB para voltar). Você perceberá que não faz ideia de onde o foco está. 
2.  **O Resgate do Foco:** No `style.css`, o desenvolvedor anterior cometeu o "pecado capital" da acessibilidade: `outline: none;` na pseudo-classe `:focus`. Altere essa regra para fornecer um contorno altamente visível (ex: uma borda grossa e pontilhada, ou um `box-shadow` marcante) sempre que um elemento interativo receber o foco.
3.  **Contraste Clandestino (Perceptibilidade):** O texto do parágrafo principal está usando a cor `#bdc3c7` (um cinza muito claro) sobre um fundo branco. Isso reprova no teste de contraste da WCAG. Altere a cor do texto para um tom mais escuro (como `#4a4a4a` ou `#333333`) para garantir a legibilidade.
4.  **Imagens Silenciosas:** No HTML, a imagem principal do artigo não possui o atributo `alt`. Adicione um texto alternativo descritivo adequado. O ícone de decoração ao lado do título também não tem o atributo; adicione um `alt=""` vazio para que seja ignorado pelos leitores de tela.
5.  **A Armadilha da Cor:** Existe uma mensagem de erro no formulário que diz "Os campos marcados em vermelho estão incorretos", mas não há nenhuma indicação em texto para daltônicos ou usuários de leitores de tela. Modifique o HTML para incluir um texto invisível visualmente (usando uma classe `.sr-only` no CSS) ou um ícone descritivo para que a cor não seja o único meio de transmitir a informação.

---

## Fontes de Consulta e Bibliografia Recomendada
* AMARAL, S. A; NASCIMENTO, J. A. M. *Avaliação de Usabilidade na internet*. Brasília: Thesaurus, 2010. (Bibliografia Básica).
* Cartilha de Acessibilidade na Web do W3C Brasil (Fascículo I).
* WCAG 2.0 (Em português) - W3C.
