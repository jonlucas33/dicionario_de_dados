# Dicionário de Dados - Schema Educacional

Este dicionário descreve as coleções (tabelas) e seus respectivos campos, incluindo tipos de dados, validações e relacionamentos.

---

### **App**
- [cite_start]**Descrição:** Tabelas do Eduprime agrupadas.
- **Campos:** Esta é uma coleção para agrupamento, não possui campos próprios.

---

### **Escolas**
- [cite_start]**Descrição:** Agrupamento para tabelas relacionadas a escolas.
- **Campos:** Esta é uma coleção para agrupamento, não possui campos próprios.

---

### **aluno**
- **Descrição:** Armazena informações sobre os alunos.
- **Campos:**
    - **id**: Identificador único (UUID).
        - [cite_start]**Validação:** Obrigatório, Único.
    - **nome**: Nome completo do aluno.
        - [cite_start]**Validação:** Obrigatório, Texto, Máximo de 100 caracteres, Apenas letras e espaços.
    - **data_de_nascimento**: Data de nascimento do aluno.
        - [cite_start]**Validação:** Obrigatório.
    - **sexo**: Sexo do aluno.
        - [cite_start]**Validação:** Obrigatório, Apenas 'Masculino' ou 'Feminino'.
    - **codigo_inep**: Código INEP do aluno.
        - [cite_start]**Validação:** Opcional, Exatamente 9 dígitos numéricos.
    - **tipo_sanguineo**: Tipo sanguíneo do aluno.
        - [cite_start]**Validação:** Opcional, Seleção entre as opções (A+, A-, B+, B-, AB+, AB-, O+, O-).
    - **numero_sus**: Número do SUS do aluno.
        - [cite_start]**Validação:** Opcional, Texto, Máximo de 100 caracteres.
    - **medicacoes_alergia**: Descrição de medicamentos para alergia.
        - [cite_start]**Validação:** Opcional, Texto, Máximo de 100 caracteres.
    - **alergia_comida**: Indica se o aluno tem alergia a alguma comida.
        - [cite_start]**Validação:** Opcional, Booleano (Verdadeiro/Falso).
    - **comidas_alergia**: Descrição das comidas às quais o aluno tem alergia.
        - [cite_start]**Validação:** Opcional, Texto, Máximo de 100 caracteres.
    - **alergia_medicacao**: Indica se o aluno tem alergia a alguma medicação.
        - [cite_start]**Validação:** Opcional, Booleano (Verdadeiro/Falso).
    - **alergia_outros**: Indica se o aluno tem outras alergias.
        - [cite_start]**Validação:** Opcional, Booleano (Verdadeiro/Falso).
    - **outros_alergia**: Descrição de outras alergias.
        - [cite_start]**Validação:** Opcional, Texto, Máximo de 100 caracteres.
    - **epiletico**, **diabetico**, **cardiaco**, **asmatico**, **hipertenso**: Indicadores de condições de saúde.
        - [cite_start]**Validação:** Opcional, Booleano (Verdadeiro/Falso).
    - **outras_doencas**: Descrição de outras doenças.
        - [cite_start]**Validação:** Opcional, Texto, Máximo de 100 caracteres.
    - **usa_medicacao_especifica**: Indica se o aluno usa medicação específica.
        - [cite_start]**Validação:** Opcional, Booleano (Verdadeiro/Falso).
    - **medicacao_especifica**: Descrição da medicação específica.
        - [cite_start]**Validação:** Opcional, Texto, Máximo de 100 caracteres.
    - **autorizacao_medicacao_emergencia**: Autorização para medicação em emergências.
        - [cite_start]**Validação:** Opcional, Booleano (Verdadeiro/Falso).
    - **nome_contato_emergencia**: Nome do contato de emergência.
        - [cite_start]**Validação:** Opcional, Texto, Máximo de 100 caracteres.
    - **telefone_contato_emergencia**: Telefone do contato de emergência.
        - [cite_start]**Validação:** Opcional, Texto, Máximo de 15 caracteres.
    - **parentesco_contato_emergencia**: Parentesco do contato de emergência.
        - [cite_start]**Validação:** Opcional, Texto, Máximo de 20 caracteres.
    - **tem_restricao_atividade_fisica**: Indica se há restrição para atividades físicas.
        - [cite_start]**Validação:** Opcional, Booleano (Verdadeiro/Falso).
    - **restricao_atividade_fisica**: Descrição da restrição para atividades físicas.
        - [cite_start]**Validação:** Opcional, Texto, Máximo de 100 caracteres.
    - **tem_plano_de_saude**: Indica se possui plano de saúde.
        - [cite_start]**Validação:** Opcional, Booleano (Verdadeiro/Falso).
    - **plano_de_saude**: Nome do plano de saúde.
        - [cite_start]**Validação:** Opcional, Texto, Máximo de 100 caracteres.
    - **email**: E-mail do aluno.
        - [cite_start]**Validação:** Opcional, Formato de e-mail válido `^[\\w\\.-]+@[\\w\\.-]+\\.\\w{2,}$`.
    - **telefone**, **telefone2**: Telefones de contato.
        - [cite_start]**Validação:** Opcional, Formato de telefone válido `^\\(?\\d{2}\\)?\\s?\\d{4,5}-?\\d{4}$`.
    - **endereco**: Endereço do aluno.
        - [cite_start]**Validação:** Opcional, Texto, Máximo de 255 caracteres.
    - **nome_guardiao**: Nome do guardião.
        - [cite_start]**Validação:** Opcional, Texto, Apenas letras e espaços, entre 3 e 100 caracteres.
    - **telefone_guardiao**: Telefone do guardião.
        - [cite_start]**Validação:** Opcional, Formato de telefone válido `^\\(?\\d{2}\\)?\\s?\\d{4,5}-?\\d{4}$`.
    - **email_guardiao**: E-mail do guardião.
        - [cite_start]**Validação:** Opcional, Formato de e-mail válido `^[\\w\\.-]+@[\\w\\.-]+\\.\\w{2,}$`.
    - **cpf_guardiao**: CPF do guardião.
        - [cite_start]**Validação:** Opcional, Formato de CPF válido `^\\d{3}\\.?\\d{3}\\.?\\d{3}-?\\d{2}$`.
    - **status**: Status do aluno.
        - [cite_start]**Validação:** Opcional, Seleção entre 'Ativo', 'Inativo', 'Graduado', 'Suspenso', 'Transferido'.
    - **escola_id**: Relacionamento com a escola.
        - [cite_start]**Validação:** Opcional, Chave estrangeira para a coleção `escola`.
    - **cep**: CEP do endereço do aluno.
        - [cite_start]**Validação:** Opcional, Formato de CEP válido `^\\d{5}-?\\d{3}$`.
    - **tipo_zona_residencia**: Tipo de zona de residência.
        - [cite_start]**Validação:** Opcional, Seleção entre 'Urbana' e 'Rural'.
    - **numero_endereco**: Número do endereço.
        - [cite_start]**Validação:** Opcional, Texto, Máximo de 100 caracteres.
    - **cpf**: CPF do aluno.
        - [cite_start]**Validação:** Opcional, Único, Formato de CPF válido `^\\d{3}\\.?\\d{3}\\.?\\d{3}-?\\d{2}$`.
    - **bairro**: Bairro do endereço.
        - [cite_start]**Validação:** Opcional, Texto, Máximo de 100 caracteres.
    - **cidade**: Cidade do endereço.
        - [cite_start]**Validação:** Opcional, Texto, Máximo de 100 caracteres.
    - **complemento**: Complemento do endereço.
        - [cite_start]**Validação:** Opcional, Texto, Máximo de 100 caracteres.
    - **nome_pai**: Nome do pai.
        - [cite_start]**Validação:** Opcional, Texto, Apenas letras e espaços, entre 3 e 100 caracteres.
    - **email_pai**: E-mail do pai.
        - [cite_start]**Validação:** Opcional, Formato de e-mail válido `^[\\w\\.-]+@[\\w\\.-]+\\.\\w{2,}$`.
    - **cpf_pai**: CPF do pai.
        - [cite_start]**Validação:** Opcional, Formato de CPF válido `^\\d{3}\\.?\\d{3}\\.?\\d{3}-?\\d{2}$`.
    - **telefone_pai**: Telefone do pai.
        - [cite_start]**Validação:** Opcional, Formato de telefone válido `^\\(?\\d{2}\\)?\\s?\\d{4,5}-?\\d{4}$`.
    - **nome_mae**: Nome da mãe.
        - [cite_start]**Validação:** Opcional, Texto, Apenas letras e espaços, entre 3 e 100 caracteres.
    - **email_mae**: E-mail da mãe.
        - [cite_start]**Validação:** Opcional, Formato de e-mail válido `^[\\w\\.-]+@[\\w\\.-]+\\.\\w{2,}$`.
    - **cpf_mae**: CPF da mãe.
        - [cite_start]**Validação:** Opcional, Formato de CPF válido `^\\d{3}\\.?\\d{3}\\.?\\d{3}-?\\d{2}$`.
    - **telefone_mae**: Telefone da mãe.
        - [cite_start]**Validação:** Opcional, Formato de telefone válido `^\\(?\\d{2}\\)?\\s?\\d{4,5}-?\\d{4}$`.
    - **numero_rg**: Número do RG.
        - [cite_start]**Validação:** Opcional, Único, Texto, Máximo de 15 caracteres.
    - **estado_rg**: Estado de emissão do RG.
        - [cite_start]**Validação:** Opcional, Texto, Máximo de 2 caracteres.
    - **data_de_expedicao**: Data de expedição do RG.
        - [cite_start]**Validação:** Opcional, Data.
    - **orgao_expedidor**: Órgão expedidor do RG.
        - [cite_start]**Validação:** Opcional, Texto, Máximo de 100 caracteres.
    - **tipo_responsavel**: Tipo de responsável pelo aluno.
        - [cite_start]**Validação:** Opcional, Seleção entre 'Pai', 'Mãe', 'Ambos', 'Outro'.
    - **certidao_de_nascimento**: Número da certidão de nascimento.
        - [cite_start]**Validação:** Opcional, Texto, Máximo de 100 caracteres.
    - **tipo_deficiencia**: Tipo de deficiência do aluno.
        - [cite_start]**Validação:** Opcional, Seleção de múltiplas opções.

---

### **bncc**
- [cite_start]**Descrição:** Armazena informações da Base Nacional Comum Curricular (BNCC).
- **Campos:**
    - **id**: Identificador único (UUID).
        - [cite_start]**Validação:** Obrigatório, Único.
    - **codigo**: Código da competência da BNCC.
        - [cite_start]**Validação:** Obrigatório, Texto.
    - **objetivo**: Objetivo de aprendizagem da BNCC.
        - [cite_start]**Validação:** Obrigatório, Texto.
    - **area_de_conhecimento**: Área de conhecimento.
        - [cite_start]**Validação:** Opcional, Texto.
    - **campos_de_acao**: Campos de ação.
        - [cite_start]**Validação:** Opcional, Texto.
    - **objetos_de_conhecimento**: Objetos de conhecimento.
        - [cite_start]**Validação:** Opcional, Texto.
    - **disciplina_id**: Relacionamento com a disciplina.
        - [cite_start]**Validação:** Obrigatório, Chave estrangeira para a coleção `disciplina`.
    - **serie_id**: Relacionamento com a série.
        - [cite_start]**Validação:** Obrigatório, Chave estrangeira para a coleção `serie`.

---

### **conteudo**
- [cite_start]**Descrição:** Armazena os conteúdos aplicados.
- **Campos:**
    - **id**: Identificador único (UUID).
        - [cite_start]**Validação:** Obrigatório, Único.
    - **data**: Data do conteúdo.
        - [cite_start]**Validação:** Obrigatório, Data e Hora.
    - **descricao**: Descrição do conteúdo.
        - [cite_start]**Validação:** Obrigatório, Texto, Máximo de 360 caracteres.
    - **turma_id**: Relacionamento com a turma.
        - [cite_start]**Validação:** Obrigatório, Chave estrangeira para a coleção `turma`.
    - **professor_id**: Relacionamento com o professor.
        - [cite_start]**Validação:** Obrigatório, Chave estrangeira para a coleção `professor`.

---

### **curso**
- [cite_start]**Descrição:** Armazena informações sobre os cursos.
- **Campos:**
    - **id**: Identificador único (UUID).
        - [cite_start]**Validação:** Obrigatório, Único.
    - **nome**: Nome do curso.
        - [cite_start]**Validação:** Obrigatório, Texto, Máximo de 10 caracteres.
    - **descricao**: Descrição do curso.
        - [cite_start]**Validação:** Opcional, Texto, Máximo de 360 caracteres.
    - **abreviacao**: Abreviação do nome do curso.
        - [cite_start]**Validação:** Opcional, Texto.
    - **nivel_ensino**: Nível de ensino do curso.
        - [cite_start]**Validação:** Obrigatório, Seleção entre 'Creche', 'Infantil', 'Fundamental', 'Médio', 'Superior'.
    - **regime_ensino**: Regime de ensino.
        - [cite_start]**Validação:** Obrigatório, Seleção entre 'Presencial', 'Semipresencial', 'EAD'.
    - **modalidade_curso**: Modalidade do curso.
        - [cite_start]**Validação:** Obrigatório, Seleção entre 'Ensino regular', 'Ensino especial', 'EJA', 'Profissionalizante'.
    - **carga_horaria**: Carga horária total do curso.
        - [cite_start]**Validação:** Obrigatório, Número inteiro.
    - **numero_de_etapas**: Número de etapas do curso.
        - [cite_start]**Validação:** Opcional, Número inteiro.
    - **serializacao**: Tipo de seriação do curso.
        - [cite_start]**Validação:** Obrigatório, Seleção entre 'Anual' e 'Creche'.
    - **instituicao_id**: Relacionamento com a instituição.
        - [cite_start]**Validação:** Obrigatório, Chave estrangeira para a coleção `instituicao`.
    - **regra_de_avaliacao_id**: Relacionamento com a regra de avaliação.
        - [cite_start]**Validação:** Obrigatório, Chave estrangeira para a coleção `regra_de_avaliacao`.

---

### **disciplina**
- [cite_start]**Descrição:** Armazena as disciplinas.
- **Campos:**
    - **id**: Identificador único (UUID).
        - [cite_start]**Validação:** Obrigatório, Único.
    - **nome**: Nome da disciplina.
        - [cite_start]**Validação:** Obrigatório, Texto.
    - **carga_horaria**: Carga horária da disciplina.
        - [cite_start]**Validação:** Obrigatório, Número inteiro.
    - **instituicao_id**: Relacionamento com a instituição.
        - [cite_start]**Validação:** Obrigatório, Chave estrangeira para a coleção `instituicao`.

---

### **escola**
- [cite_start]**Descrição:** Informações básicas de escola.
- **Campos:**
    - **id**: Identificador único (UUID).
        - [cite_start]**Validação:** Obrigatório, Único.
    - **nome**: Nome da escola.
        - [cite_start]**Validação:** Obrigatório, Texto, Máximo de 20 caracteres.
    - **razao_social**: Razão social da escola.
        - [cite_start]**Validação:** Opcional, Texto.
    - **sigla**: Sigla da escola.
        - [cite_start]**Validação:** Opcional, Texto, Máximo de 10 caracteres.
    - **cnpj**: CNPJ da escola.
        - [cite_start]**Validação:** Opcional, Exatamente 14 dígitos numéricos.
    - **codigo_inep**: Código INEP da escola.
        - [cite_start]**Validação:** Opcional, Exatamente 8 dígitos numéricos.
    - **idpes**: Identificador da escola.
        - [cite_start]**Validação:** Opcional, Número inteiro.
    - **instituicao_id**: Relacionamento com a instituição.
        - [cite_start]**Validação:** Obrigatório, Chave estrangeira para a coleção `instituicao`.

---

### **frequencia**
- [cite_start]**Descrição:** Registros de frequência.
- **Campos:**
    - **id**: Identificador único (UUID).
        - [cite_start]**Validação:** Obrigatório, Único.
    - **data**: Data da aula/frequência.
        - [cite_start]**Validação:** Obrigatório, Data.
    - **presenca**: Indica se o aluno esteve presente.
        - [cite_start]**Validação:** Obrigatório, Booleano (Verdadeiro/Falso).
    - [cite_start]**professor_id**, **aluno_id**, **turma_id**, **matricula_id**, **etapa_id**, **escola_id**: Chaves estrangeiras obrigatórias para `professor`, `aluno`, `turma`, `matricula`, `etapa` e `escola`.
    - **disciplina_id**: Relacionamento com disciplina.
        - [cite_start]**Validação:** Opcional, Chave estrangeira para `disciplina`.
    - **justicativa_id**: Relacionamento com justificativa de falta.
        - [cite_start]**Validação:** Opcional, Chave estrangeira para `justificativa`.

---

### **matricula**
- [cite_start]**Descrição:** Registros de matrícula dos alunos.
- **Campos:**
    - **id**: Identificador único (UUID).
        - [cite_start]**Validação:** Obrigatório, Único.
    - **nome**: Nome associado à matrícula.
        - [cite_start]**Validação:** Obrigatório, Texto, Máximo de 100 caracteres.
    - **codigo_de_matricula**: Código da matrícula.
        - [cite_start]**Validação:** Obrigatório, Texto, Máximo de 100 caracteres.
    - **data_matricula**: Data da realização da matrícula.
        - [cite_start]**Validação:** Obrigatório, Data e Hora.
    - **situacao**: Situação atual da matrícula.
        - [cite_start]**Validação:** Obrigatório, Seleção de opções como 'PENDENTE', 'CURSANDO', 'APROVADO', etc..
    - **status**: Status da matrícula.
        - [cite_start]**Validação:** Opcional, Seleção de opções como 'ativo', 'Inativo', 'Graduado', etc..
    - [cite_start]**escola_id**, **aluno_id**, **curso_id**, **turma_id**, **series_id**: Chaves estrangeiras obrigatórias para `escola`, `aluno`, `curso`, `turma` e `serie`.
    - **pre_matricula_id**: Relacionamento com pré-matrícula.
        - [cite_start]**Validação:** Opcional, Chave estrangeira única para `pre_matricula`.
    - **instituicao_id**: Relacionamento com instituição.
        - [cite_start]**Validação:** Opcional, Chave estrangeira para `instituicao`.
    - **observacoes**: Observações sobre a matrícula.
        - [cite_start]**Validação:** Opcional, Texto, Máximo de 200 caracteres.

---

### **professor**
- [cite_start]**Descrição:** Armazena informações sobre os professores.
- **Campos:**
    - **id**: Identificador único (UUID).
        - [cite_start]**Validação:** Obrigatório, Único.
    - **nome**: Nome do professor.
        - [cite_start]**Validação:** Obrigatório, Texto, Apenas letras e espaços, entre 3 e 100 caracteres.
    - **codigo_inep**: Código INEP do professor.
        - [cite_start]**Validação:** Obrigatório, Exatamente 9 dígitos numéricos.
    - **data_nascimento**: Data de nascimento do professor.
        - [cite_start]**Validação:** Obrigatório, Data.
    - **email**: E-mail do professor.
        - [cite_start]**Validação:** Opcional, Formato de e-mail válido `^[\\w\\.-]+@[\\w\\.-]+\\.\\w{2,}$`.
    - **telefone**: Telefone do professor.
        - [cite_start]**Validação:** Opcional, Formato de telefone válido `^\\(?\\d{2}\\)?\\s?\\d{4,5}-?\\d{4}$`.
    - **endereco**: Endereço do professor.
        - [cite_start]**Validação:** Opcional, Texto, Máximo de 255 caracteres.
    - **status**: Status do professor.
        - [cite_start]**Validação:** Opcional, Seleção entre 'ATIVO', 'INATIVO', etc..

---

### **regra_de_avaliacao**
- [cite_start]**Descrição:** Regras aplicáveis a um curso.
- **Campos:**
    - **id**: Identificador único (UUID).
        - [cite_start]**Validação:** Obrigatório, Único.
    - **nome**: Nome da regra de avaliação.
        - [cite_start]**Validação:** Obrigatório, Texto.
    - **tipo_nota**: Como a nota será registrada.
        - [cite_start]**Validação:** Obrigatório, Seleção de opções como 'Numérica', 'Conceitual', etc..
    - **nota_minima**: Nota mínima para aprovação.
        - [cite_start]**Validação:** Obrigatório, Número decimal.
    - **nota_maxima**: Nota máxima possível.
        - [cite_start]**Validação:** Obrigatório, Número decimal.
    - **media**: Média para aprovação.
        - [cite_start]**Validação:** Obrigatório, Número decimal.
    - **casas_decimais**: Número de casas decimais para as notas.
        - [cite_start]**Validação:** Obrigatório, Número inteiro.
    - **formula_media**: Fórmula para cálculo da média final.
        - [cite_start]**Validação:** Obrigatório, Seleção de opções como 'Média aritmética', etc..
    - **tipo_frequencia**: Como a frequência é calculada.
        - [cite_start]**Validação:** Obrigatório, Seleção entre 'Diária' e 'Disciplina'.
    - **usa_frequencia_para_passar**: Define se a frequência é critério de aprovação.
        - [cite_start]**Validação:** Obrigatório, Booleano.
    - **porcentagem_frequencia**: Porcentagem mínima de frequência.
        - [cite_start]**Validação:** Obrigatório, Número decimal.
    - **numero_atividades**: Quantidade de atividades avaliativas.
        - [cite_start]**Validação:** Obrigatório, Número inteiro.
    - **formula_recuperacao**: Como a nota de recuperação é calculada.
        - [cite_start]**Validação:** Obrigatório, Seleção de múltiplas opções.
    - **tipo_parecer**: Como o parecer descritivo é aplicado.
        - [cite_start]**Validação:** Obrigatório, Seleção de múltiplas opções.
    - **tipo_progressao**: Como o aluno progride de ano/série.
        - [cite_start]**Validação:** Obrigatório, Seleção de múltiplas opções.
    - **recuperacao_paralela**: Como a recuperação paralela funciona.
        - [cite_start]**Validação:** Obrigatório, Seleção de múltiplas opções.
    - **instituicao_id**: Relacionamento com a instituição.
        - [cite_start]**Validação:** Obrigatório, Chave estrangeira para a coleção `instituicao`.

---

### **serie**
- [cite_start]**Descrição:** Armazena as séries/anos dos cursos.
- **Campos:**
    - **id**: Identificador único (UUID).
        - [cite_start]**Validação:** Obrigatório, Único.
    - **nome**: Nome da série.
        - [cite_start]**Validação:** Obrigatório, Texto.
    - **idade_padrao**, **idade_minima**, **idade_maxima**: Idades de referência para a série.
        - [cite_start]**Validação:** Obrigatório, Número inteiro.
    - **bloquear_idade_fora_do_limite**: Bloqueia matrícula de alunos com idade fora do limite.
        - [cite_start]**Validação:** Obrigatório, Booleano.
    - **alertar_idade_fora_do_limite**: Alerta sobre alunos com idade fora do limite.
        - [cite_start]**Validação:** Obrigatório, Booleano.
    - **carga_horaria**: Carga horária da série.
        - [cite_start]**Validação:** Opcional, Número inteiro.
    - **curso_id**: Relacionamento com o curso.
        - [cite_start]**Validação:** Obrigatório, Chave estrangeira para a coleção `curso`.

---

### **turma**
- [cite_start]**Descrição:** Armazena as turmas.
- **Campos:**
    - **id**: Identificador único (UUID).
        - [cite_start]**Validação:** Obrigatório, Único.
    - **nome**: Nome da turma.
        - [cite_start]**Validação:** Obrigatório, Texto.
    - **abreviacao**: Abreviação do nome da turma.
        - [cite_start]**Validação:** Opcional, Texto.
    - **codigo_inep**: Código INEP da turma.
        - [cite_start]**Validação:** Opcional, Exatamente 12 dígitos numéricos.
    - **sala**: Sala da turma.
        - [cite_start]**Validação:** Opcional, Texto.
    - **ano**: Ano letivo da turma.
        - [cite_start]**Validação:** Obrigatório, Número inteiro (mínimo 2000).
    - **periodo**: Período da turma.
        - [cite_start]**Validação:** Obrigatório, Seleção entre 'Manhã', 'Tarde', 'Noite', 'Integral'.
    - **estudantes_max**, **estudantes_excesso**, **estudantes_pcd**: Limites de estudantes na turma.
        - [cite_start]**Validação:** Obrigatório, Número inteiro.
    - **dias_da_semana**: Dias em que a turma tem aula.
        - [cite_start]**Validação:** Obrigatório, Seleção de múltiplas opções.
    - **multiseriado**, **lista_alternativa_disciplinas**: Indicadores de características da turma.
        - [cite_start]**Validação:** Opcional, Booleano.
    - [cite_start]**escola_id**, **serie_id**: Chaves estrangeiras obrigatórias para `escola` e `serie`.

---

*Observação: Campos como `user_created`, `date_created`, `user_updated`, e `date_updated` são de sistema, preenchidos automaticamente e não foram detalhados.*
