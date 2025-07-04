# Dicionário de Dados - Schema Educacional

Este dicionário descreve as coleções (tabelas) e seus respectivos campos, incluindo tipos de dados, validações e relacionamentos.

---

### **App**
- **Descrição:** Tabelas do Eduprime agrupadas.
- **Campos:** Esta é uma coleção para agrupamento, não possui campos próprios.

---

### **Escolas**
- **Descrição:** Agrupamento para tabelas relacionadas a escolas.
- **Campos:** Esta é uma coleção para agrupamento, não possui campos próprios.

---

### **aluno**
- **Descrição:** Armazena informações sobre os alunos.
- **Campos:**
    - **id**: Identificador único (UUID).
        - **Validação:** Obrigatório, Único.
    - **nome**: Nome completo do aluno.
        - **Validação:** Obrigatório, String, Minímo 3 caracteres e Máximo de 100 caracteres, Apenas letras e espaços.
    - **data_de_nascimento**: Data de nascimento do aluno.
        - **Validação:** Obrigatório.
    - **sexo**: Sexo do aluno.
        - **Validação:** Obrigatório, Apenas 'Masculino' ou 'Feminino'.
    - **codigo_inep**: Código INEP do aluno.
        - **Validação:** Opcional, Exatamente 12 dígitos numéricos.
    - **tipo_sanguineo**: Tipo sanguíneo do aluno.
        - **Validação:** Opcional, Seleção entre as opções (A+, A-, B+, B-, AB+, AB-, O+, O-).
    - **numero_sus**: Número do SUS do aluno.
        - **Validação:** Opcional, Texto, Máximo de 100 caracteres.
    - **alergia_medicacao**: Indica se o aluno tem alergia a alguma medicação.
        - **Validação:** Opcional, Booleano (Verdadeiro/Falso).
    - **medicacoes_alergia**: Descrição de medicamentos para alergia.
        - **Validação:** Opcional, Texto, Máximo de 100 caracteres.
    - **alergia_comida**: Indica se o aluno tem alergia a alguma comida.
        - **Validação:** Opcional, Booleano (Verdadeiro/Falso).
    - **comidas_alergia**: Descrição das comidas às quais o aluno tem alergia.
        - **Validação:** Opcional, Texto, Máximo de 100 caracteres.
    - **alergia_outros**: Indica se o aluno tem outras alergias.
        - **Validação:** Opcional, Booleano (Verdadeiro/Falso).
    - **outros_alergia**: Descrição de outras alergias.
        - **Validação:** Opcional, Texto, Máximo de 100 caracteres.
    - **epiletico**, **diabetico**, **cardiaco**, **asmatico**, **hipertenso**: Indicadores de condições de saúde.
        - **Validação:** Opcional, Booleano (Verdadeiro/Falso).
    - **outras_doencas**: Descrição de outras doenças.
        - **Validação:** Opcional, Texto, Máximo de 100 caracteres.
    - **usa_medicacao_especifica**: Indica se o aluno usa medicação específica.
        - **Validação:** Opcional, Booleano (Verdadeiro/Falso).
    - **medicacao_especifica**: Descrição da medicação específica.
        - **Validação:** Opcional, Texto, Máximo de 100 caracteres.
    - **autorizacao_medicacao_emergencia**: Autorização para medicação em emergências.
        - **Validação:** Opcional, Booleano (Verdadeiro/Falso).
    - **nome_contato_emergencia**: Nome do contato de emergência.
        - **Validação:** Opcional, String, Minímo 3 caracteres e Máximo de 100 caracteres, Apenas letras e espaços.
    - **telefone_contato_emergencia**: Telefone do contato de emergência.
        - **Validação:** Opcional, String, Máximo de 11 caracteres. Formato de telefone válido `^\\(?\\d{2}\\)?\\s?\\d{4,5}-?\\d{4}$`.
    - **parentesco_contato_emergencia**: Parentesco do contato de emergência.
        - **Validação:** Opcional, Texto, Máximo de 20 caracteres.
    - **tem_restricao_atividade_fisica**: Indica se há restrição para atividades físicas.
        - **Validação:** Opcional, Booleano (Verdadeiro/Falso).
    - **restricao_atividade_fisica**: Descrição da restrição para atividades físicas.
        - **Validação:** Opcional, Texto, Máximo de 100 caracteres.
    - **tem_plano_de_saude**: Indica se possui plano de saúde.
        - **Validação:** Opcional, Booleano (Verdadeiro/Falso).
    - **plano_de_saude**: Nome do plano de saúde.
        - **Validação:** Opcional, Texto, Máximo de 100 caracteres.
    - **email**: E-mail do aluno.
        - **Validação:** Opcional, String, Máximo de 255 caracteres. Formato de e-mail válido `^[\\w\\.-]+@[\\w\\.-]+\\.\\w{2,}$`.
    - **telefone**, **telefone_2**: Telefones de contato.
        - **Validação:** Opcional, String, Máximo de 11 caracteres. Formato de telefone válido `^\\(?\\d{2}\\)?\\s?\\d{4,5}-?\\d{4}$`.
    - **endereco**: Endereço do aluno.
        - **Validação:** Opcional, String, Máximo de 255 caracteres.
    - **nome_guardiao**: Nome do guardião.
        - **Validação:** Opcional, String, Apenas letras e espaços, entre 3 e 100 caracteres.
    - **telefone_guardiao**: Telefone do guardião.
        - **Validação:** Opcional, String, Máximo de 11 caracteres. Formato de telefone válido `^\\(?\\d{2}\\)?\\s?\\d{4,5}-?\\d{4}$`.
    - **email_guardiao**: E-mail do guardião.
        - **Validação:** Opcional, String, Máximo de 255 caracteres. Formato de e-mail válido `^[\\w\\.-]+@[\\w\\.-]+\\.\\w{2,}$`.
    - **cpf_guardiao**: CPF do guardião.
        - **Validação:** Opcional, String, Máximo de 11 caracteres. Formato de CPF válido `^\\d{3}\\.?\\d{3}\\.?\\d{3}-?\\d{2}$`.
    - **status**: Status do aluno.
        - **Validação:** Obrigatório, Seleção entre 'Ativo', 'Inativo', 'Graduado', 'Suspenso', 'Transferido'.
    - **escola_id**: Relacionamento com a escola.
        - **Validação:** Obrigatório, Chave estrangeira para a coleção `escola`.
    - **cep**: CEP do endereço do aluno.
        - **Validação:** Obrigatório, String, Máximo de 8 caracteres. Formato de CEP válido `^\\d{5}-?\\d{3}$`.
    - **tipo_zona_residencia**: Tipo de zona de residência.
        - **Validação:** Opcional, Seleção entre 'Urbana' e 'Rural'.
    - **numero_endereco**: Número do endereço.
        - **Validação:** Opcional, String, Máximo de 100 caracteres.
    - **cpf**: CPF do aluno.
        - **Validação:** Opcional, Único, Formato de CPF válido `^\\d{3}\\.?\\d{3}\\.?\\d{3}-?\\d{2}$`.
    - **bairro**: Bairro do endereço.
        - **Validação:** Opcional, String, Máximo de 100 caracteres.
    - **cidade**: Cidade do endereço.
        - **Validação:** Opcional, String, Máximo de 100 caracteres.
    - **complemento**: Complemento do endereço.
        - **Validação:** Opcional, String, Máximo de 100 caracteres.
    - **nome_pai**: Nome do pai.
        - **Validação:** Opcional, Texto, Apenas letras e espaços, entre 3 e 100 caracteres.
    - **email_pai**: E-mail do pai.
        - **Validação:** Opcional, String, Máximo de 255 caracteres. Formato de e-mail válido `^[\\w\\.-]+@[\\w\\.-]+\\.\\w{2,}$`.
    - **cpf_pai**: CPF do pai.
        - **Validação:** Opcional, String, Máximo de 11 caracteres. Formato de CPF válido `^\\d{3}\\.?\\d{3}\\.?\\d{3}-?\\d{2}$`.
    - **telefone_pai**: Telefone do pai.
        - **Validação:** Opcional, String, Máximo de 11 caracteres. Formato de telefone válido `^\\(?\\d{2}\\)?\\s?\\d{4,5}-?\\d{4}$`.
    - **nome_mae**: Nome da mãe.
        - **Validação:** Opcional, String, Minímo 3 caracteres e Máximo de 100 caracteres, Apenas letras e espaços.
    - **email_mae**: E-mail da mãe.
        - **Validação:** Opcional, String, Máximo de 255 caracteres. Formato de e-mail válido `^[\\w\\.-]+@[\\w\\.-]+\\.\\w{2,}$`.
    - **cpf_mae**: CPF da mãe.
        - **Validação:** Opcional, String, Máximo de 11 caracteres. Formato de CPF válido `^\\d{3}\\.?\\d{3}\\.?\\d{3}-?\\d{2}$`.
    - **telefone_mae**: Telefone da mãe.
        - **Validação:** Opcional, String, Máximo de 11 caracteres. Formato de telefone válido `^\\(?\\d{2}\\)?\\s?\\d{4,5}-?\\d{4}$`.
    - **numero_rg**: Número do RG.
        - **Validação:** Opcional, String, Máximo de 15 caracteres.
    - **estado_rg**: Estado de emissão do RG.
        - **Validação:** Opcional, Seleção entre multiplas opções, que são as siglas de todos os estados brasileiros.
    - **data_de_expedicao**: Data de expedição do RG.
        - **Validação:** Opcional, Data.
    - **orgao_expedidor**: Órgão expedidor do RG.
        - **Validação:** Opcional, String, Máximo de 100 caracteres.
    - **tipo_responsavel**: Tipo de responsável pelo aluno.
        - **Validação:** Opcional, Seleção entre 'Pai', 'Mãe', 'Ambos', 'Outro'.
    - **certidao_de_nascimento**: Número da certidão de nascimento.
        - **Validação:** Opcional, Texto, Máximo de 100 caracteres.
    - **tipo_deficiencia**: Tipo de deficiência do aluno.
        - **Validação:** Opcional, Seleção entre múltiplas opções.
    - **feedback_aluno**: Relacionamento com a feedback_aluno.
        - **Validação:** Opcional, Chave estrangeira para a coleção 'feedback-aluno'.
    - **nota_numerica**: Relacionamento com a nota_numerica.
        - **Validação:** Opcional, Chave estrangeira para a coleção 'nota_numerica'.
    - **nota_disciplina**: Relacionamento com a nota_disciplina.
        - **Validação:** Opcional, Chave estrangeira para a coleção 'nota_disciplina'.

---

### **bncc**
- **Descrição:** Armazena informações da Base Nacional Comum Curricular (BNCC).
- **Campos:**
    - **id**: Identificador único (UUID).
        - **Validação:** Obrigatório, Único.
    - **codigo**: Código da competência da BNCC.
        - **Validação:** Obrigatório, String, Máximo de 255 caracteres.
    - **objetivo**: Objetivo de aprendizagem da BNCC.
        - **Validação:** Obrigatório, Texto.
    - **area_de_conhecimento**: Área de conhecimento.
        - **Validação:** Opcional, String, Máximo de 255 caracteres.
    - **campos_de_acao**: Campos de ação.
        - **Validação:** Opcional, String, Máximo de 255 caracteres.
    - **objetos_de_conhecimento**: Objetos de conhecimento.
        - **Validação:** Opcional, String, Máximo de 255 caracteres.
    - **disciplina_id**: Relacionamento com a disciplina.
        - **Validação:** Obrigatório, Chave estrangeira para a coleção `disciplina`.
    - **serie_id**: Relacionamento com a série.
        - **Validação:** Obrigatório, Chave estrangeira para a coleção `serie`.
    - **date_created**: Campo apenas para visualização da data de criação da BNCC.
    - **user_created**: Relacionamento com directus_users.
    - **date_updated**: Campo apenas para visualização da data de atualização da BNCC.
    - **user_updated**: Relacionamento com directus_users.
---

### **conteudo**
- **Descrição:** Armazena os conteúdos aplicados.
- **Campos:**
    - **id**: Identificador único (UUID).
        - **Validação:** Obrigatório, Único.
    - **data**: Data do conteúdo.
        - **Validação:** Obrigatório, Data e Hora.
    - **descricao**: Descrição do conteúdo.
        - **Validação:** Obrigatório, Texto, Máximo de 360 caracteres.
    - **turma_id**: Relacionamento com a turma.
        - **Validação:** Obrigatório, Chave estrangeira para a coleção `turma`.
    - **professor_id**: Relacionamento com o professor.
        - **Validação:** Obrigatório, Chave estrangeira para a coleção `professor`.
    - **date_created**: Campo apenas para visualização da data de criação do conteúdo.
    - **user_created**: Relacionamento com directus_users.
    - **date_updated**: Campo apenas para visualização da data de atualização do conteúdo.
    - **user_updated**: Relacionamento com directus_users.
    - **conteudo_bncc**: Relacionamento com bncc.
    - **conteudo_disciplina**: Relacionamento com disciplina.
---

### **curso**
- **Descrição:** Armazena informações sobre os cursos.
- **Campos:**
    - **id**: Identificador único (UUID).
        - **Validação:** Obrigatório, Único.
    - **nome**: Nome do curso.
        - **Validação:** Obrigatório, String, Máximo de 255 caracteres.
    - **descricao**: Descrição do curso.
        - **Validação:** Opcional, Texto, Máximo de 360 caracteres.
    - **abreviacao**: Abreviação do nome do curso.
        - **Validação:** Opcional, String, Máximo de 255 caracteres.
    - **nivel_ensino**: Nível de ensino do curso.
        - **Validação:** Obrigatório, Seleção entre 'Creche', 'Infantil', 'Fundamental', 'Médio', 'Superior'.
    - **regime_ensino**: Regime de ensino.
        - **Validação:** Obrigatório, Seleção entre 'Presencial', 'Semipresencial' e 'EAD'.
    - **modalidade_curso**: Modalidade do curso.
        - **Validação:** Obrigatório, Seleção entre 'Ensino regular', 'Ensino especial', 'EJA', 'Profissionalizante'.
    - **carga_horaria**: Carga horária total do curso.
        - **Validação:** Obrigatório, Número inteiro.
    - **numero_de_etapas**: Número de etapas do curso.
        - **Validação:** Opcional, Número inteiro.
    - **serializacao**: Tipo de seriação do curso.
        - **Validação:** Obrigatório, Seleção entre 'Anual' e 'Creche'.
    - **instituicao_id**: Relacionamento com a instituição.
        - **Validação:** Obrigatório, Chave estrangeira para a coleção `instituicao`.
    - **regra_de_avaliacao_id**: Relacionamento com a regra de avaliação.
        - **Validação:** Obrigatório, Chave estrangeira para a coleção `regra_de_avaliacao`.
    - **date_created**: Campo apenas para visualização da data de criação do curso.
    - **user_created**: Relacionamento com directus_users.
    - **date_updated**: Campo apenas para visualização da data de atualização do curso.
    - **user_updated**: Relacionamento com directus_users.
    - **matricula**: Relacionamento com matricula através da chave forte 'curso_id'.
    - **pre_matricula**: Relacionamento com pre_matricula através da chave forte 'curso_id'.
    - **curso_escola**: Relacionamento com escola.

---

### **disciplina**
- **Descrição:** Armazena as disciplinas.
- **Campos:**
    - **id**: Identificador único (UUID).
        - **Validação:** Obrigatório, Único.
    - **nome**: Nome da disciplina.
        - **Validação:** Obrigatório, String, Máximo de 255 caracteres.
    - **carga_horaria**: Carga horária da disciplina.
        - **Validação:** Obrigatório, Número inteiro.
    - **instituicao_id**: Relacionamento com a instituição.
        - **Validação:** Obrigatório, Chave estrangeira para a coleção 'instituicao'.
    - **date_created**: Campo apenas para visualização da data de criação da disciplina.
    - **user_created**: Relacionamento com directus_users.
    - **date_updated**: Campo apenas para visualização da data de atualização da disciplina.
    - **user_updated**: Relacionamento com directus_users.
    - **nota_registrada**: Relacionamento com nota_registrada através da chave forte 'disciplina_id'.
    - **professor_disciplina**: Relacionamento com professor_disciplina.
    - **nota_conceitual**: Relacionamento com nota_conceitual através da chave forte 'disciplina_id'.
    - **frequencia**: Relacionamento com frequencia através da chave forte 'disciplina_id'.
    - **frequencia_disciplina**: Relacionamento com frequencia_disciplina através da chave forte 'disciplina_id'.
    - **frequencia_professor**: Relacionamento com frequencia_professor através da chave forte 'disciplina_id'.
    - **feedback_aluno**: Relacionamento com feedback_aluno através da chave forte 'disciplina_id'.
    - **nota_numerica**: Relacionamento com numerica através da chave forte 'disciplina_id'.
    - **nota_disciplina**: Relacionamento com disciplina através da chave forte 'disciplina_id'.
---

### **escola**
- **Descrição:** Informações básicas de escola.
- **Campos:**
    - **id**: Identificador único (UUID).
        - **Validação:** Obrigatório, Único.
    - **nome**: Nome da escola.
        - **Validação:** Obrigatório, String, Máximo de 255 caracteres.
    - **razao_social**: Razão social da escola.
        - **Validação:** Opcional, String, Máximo de 255 caracteres.
    - **sigla**: Sigla da escola.
        - **Validação:** Opcional, Texto, Máximo de 10 caracteres.
    - **cnpj**: CNPJ da escola.
        - **Validação:** Obrigatório, Exatamente 14 dígitos numéricos.
    - **codigo_inep**: Código INEP da escola.
        - **Validação:** Opcional, Exatamente 8 dígitos numéricos.
    - **idpes**: Identificador da escola.
        - **Validação:** Opcional, Número inteiro.
    - **instituicao_id**: Relacionamento com a instituição.
        - **Validação:** Obrigatório, Chave estrangeira para a coleção 'instituicao'.
    - **cep**: CEP do endereço da escola.
        - **Validação:** Obrigatório, String, Máximo de 8 caracteres. Formato de CEP válido `^\\d{5}-?\\d{3}$`.
    - **endereco**: Endereço da escola.
        - **Validação:** Opcional, String, Máximo de 255 caracteres.
    - **numero_endereco**: Número do endereço.
        - **Validação:** Opcional, String, Máximo de 100 caracteres.
    - **complemento**: Complemento do endereço.
        - **Validação:** Opcional, String, Máximo de 100 caracteres. 
    - **bairro**: Bairro do endereço.
        - **Validação:** Opcional, String, Máximo de 100 caracteres.
    - **cidade**: Cidade do endereço.
        - **Validação:** Opcional, String, Máximo de 100 caracteres.
    - **estado**: Estado do endereço.
        - **Validação:** Opcional, Seleção entre multiplas opções, que são as siglas de todos os estados brasileiros.
    - **telefone** e **telefone_2**: Telefones de contato da escola.
        - **Validação:** Opcional, String, Máximo de 11 caracteres. Formato de telefone válido `^\\(?\\d{2}\\)?\\s?\\d{4,5}-?\\d{4}$`.
    - **instituicao_id**: Relacionamento com a instituição.
        - **Validação:** Obrigatório, Chave estrangeira para a coleção 'instituicao'.
    - **date_created**: Campo apenas para visualização da data de criação da disciplina.
    - **user_created**: Relacionamento com directus_users.
    - **date_updated**: Campo apenas para visualização da data de atualização da disciplina.
    - **user_updated**: Relacionamento com directus_users.
    - **matricula**: Relacionamento com matricula através da chave forte 'escola_id'.
    - **escola_professor**: Relacionamento com professor.
    - **pre_matricula**: Relacionamento com pre_matricula através da chave forte 'escola_id'.
    - **nota_geral**: Relacionamento com nota_geral através da chave forte 'escola_id'.
    - **nota_conceitual**: Relacionamento com nota_conceitual através da chave forte 'escola_id'.
    - **frequencia**: Relacionamento com frequencia através da chave forte 'escola_id'.
    - **frequencia_aluno**: Relacionamento com frequencia_aluno através da chave forte 'escola_id'.
    - **frequencia_geral**: Relacionamento com frequencia_geral através da chave forte 'escola_id'.
    - **frequencia_disciplina**: Relacionamento com frequencia_disciplina através da chave forte 'escola_id'.
    - **frequencia_professor**: Relacionamento com frequencia_professor através da chave forte 'escola_id'.
    - **aluno**: Relacionamento com aluno através da chave forte 'escola_id'.
    - **servidor**: Relacionamento com servidor através da chave forte 'escola_id'.
    - **feedback_aluno**: Relacionamento com feedback_aluno através da chave forte 'escola_id'.
    - **nota_numerica**: Relacionamento com numerica através da chave forte 'escola_id'.
    - **nota_disciplina**: Relacionamento com disciplina através da chave forte 'escola_id'.
---

### **frequencia**
- **Descrição:** Registros de frequência.
- **Campos:**
    - **id**: Identificador único (UUID).
        - **Validação:** Obrigatório, Único.
    - **data**: Data da aula/frequência.
        - **Validação:** Obrigatório, Data.
    - **presenca**: Indica se o aluno esteve presente.
        - **Validação:** Obrigatório, Booleano (Verdadeiro/Falso).
    - **professor_id**, **aluno_id**, **turma_id**, **matricula_id**, **etapa_id**, **escola_id**: Chaves estrangeiras obrigatórias para `professor`, `aluno`, `turma`, `matricula`, `etapa` e `escola`.
    - **disciplina_id**: Relacionamento com disciplina.
        - **Validação:** Opcional, Chave estrangeira para `disciplina`.
    - **justicativa_id**: Relacionamento com justificativa de falta.
        - **Validação:** Opcional, Chave estrangeira para `justificativa`.

---

### **matricula**
- **Descrição:** Registros de matrícula dos alunos.
- **Campos:**
    - **id**: Identificador único (UUID).
        - **Validação:** Obrigatório, Único.
    - **nome**: Nome associado à matrícula.
        - **Validação:** Obrigatório, String, Apenas letras e espaços, entre 3 e 100 caracteres.
    - **codigo_de_matricula**: Código da matrícula.
        - **Validação:** Obrigatório, String, Máximo de 100 caracteres.
    - **data_matricula**: Data da realização da matrícula.
        - **Validação:** Obrigatório, Data e Hora.
    - **situacao**: Situação atual da matrícula.
        - **Validação:** Obrigatório, String, Seleção entre as opções 'PENDENTE', 'CURSANDO', 'APROVADO', etc..
    - **status**: Status da matrícula.
        - **Validação:** Opcional, String, Seleção entre as opções 'ativo', 'Inativo', 'Graduado', etc..
    - **escola_id**, **aluno_id**, **curso_id**, **turma_id**, **series_id**: Chaves estrangeiras obrigatórias para `escola`, `aluno`, `curso`, `turma` e `serie`.
    - **pre_matricula_id**: Relacionamento com pré-matrícula.
        - **Validação:** Opcional, Chave estrangeira única para `pre_matricula`.
    - **instituicao_id**: Relacionamento com instituição.
        - **Validação:** Opcional, Chave estrangeira para `instituicao`.
    - **observacoes**: Observações sobre a matrícula.
        - **Validação:** Opcional, String, Máximo de 200 caracteres.

---

### **professor**
- **Descrição:** Armazena informações sobre os professores.
- **Campos:**
    - **id**: Identificador único (UUID).
        - **Validação:** Obrigatório, Único.
    - **nome**: Nome do professor.
        - **Validação:** Obrigatório, String, Apenas letras e espaços, entre 3 e 100 caracteres.
    - **codigo_inep**: Código INEP do professor.
        - **Validação:** Obrigatório, String, Exatamente 12 dígitos numéricos.
    - **data_nascimento**: Data de nascimento do professor.
        - **Validação:** Obrigatório, Data.
    - **email**: E-mail do professor.
        - **Validação:** Opcional, String, Máximo de 255 caracteres. Formato de e-mail válido ^[\\w\\.-]+@[\\w\\.-]+\\.\\w{2,}$.
    - **telefone**: Telefone do professor.
        - **Validação:** Opcional, String, Formato de telefone válido `^\\(?\\d{2}\\)?\\s?\\d{4,5}-?\\d{4}$`.
    - **endereco**: Endereço do professor.
        - **Validação:** Opcional, String, Máximo de 255 caracteres.
    - **status**: Status do professor.
        - **Validação:** Opcional, String, Seleção entre as opções 'ATIVO', 'INATIVO', etc..

---

### **regra_de_avaliacao**
- **Descrição:** Regras aplicáveis a um curso.
- **Campos:**
    - **id**: Identificador único (UUID).
        - **Validação:** Obrigatório, Único.
    - **nome**: Nome da regra de avaliação.
        - **Validação:** Obrigatório, String, Máximo de 100 caracteres.
    - **tipo_nota**: Como a nota será registrada.
        - **Validação:** Obrigatório, String, Seleção entre as opções 'Numérica', 'Conceitual', etc..
    - **nota_minima**: Nota mínima para aprovação.
        - **Validação:** Obrigatório, Número decimal.
    - **nota_maxima**: Nota máxima possível.
        - **Validação:** Obrigatório, Número decimal.
    - **media**: Média para aprovação.
        - **Validação:** Obrigatório, Número decimal.
    - **casas_decimais**: Número de casas decimais para as notas.
        - **Validação:** Obrigatório, Número inteiro.
    - **formula_media**: Fórmula para cálculo da média final.
        - **Validação:** Obrigatório, String, Seleção entre as opções 'Média aritmética', etc.
    - **arredondamento_por_etapa**: Arredondamento por Etapa
        - **Validação:** Obrigatório, String, Seleção entre as opções 'Arededondar para o inteiro mais próximo', etc.
    - **arredondamento_geral**
        - **Validação:** Obrigatório, String, Seleção entre as opções 'Arededondar para o inteiro mais próximo', etc.
    - **tipo_frequencia**: Como a frequência é calculada.
        - **Validação:** Obrigatório, String, Botão de seleção única entre 'Diária' e 'Disciplina'.
    - **usa_frequencia_para_passar**: Define se a frequência é critério de aprovação.
        - **Validação:** Obrigatório, Booleano.
    - **porcentagem_frequencia**: Porcentagem mínima de frequência.
        - **Validação:** Obrigatório, Número decimal.
    - **numero_atividades**: Quantidade de atividades avaliativas.
        - **Validação:** Obrigatório, Número inteiro.
    - **formula_recuperacao**: Como a nota de recuperação é calculada.
        - **Validação:** Obrigatório, String, Seleção entre as opções 'Recuperação soma com atividades', etc.
    - **tipo_parecer**: Como o parecer descritivo é aplicado.
        - **Validação:** Obrigatório, String, Seleção entre as opções 'Um parecer por etapa, geral', etc.
    - **tipo_progressao**: Como o aluno progride de ano/série.
        - **Validação:** Obrigatório, String, Seleção entre as opções 'Continuada', 'Não continuada', etc.
    - **recuperacao_paralela**: Como a recuperação paralela funciona.
        - **Validação:** Obrigatório, String, Seleção entre as opções 'Não usar recuperação paralela', etc.
    - **instituicao_id**: Relacionamento com a instituição.
        - **Validação:** Obrigatório, Chave estrangeira para a coleção `instituicao`.

---

### **serie**
- **Descrição:** Armazena as séries/anos dos cursos.
- **Campos:**
    - **id**: Identificador único (UUID).
        - **Validação:** Obrigatório, Único.
    - **nome**: Nome da série.
        - **Validação:** Obrigatório, String, Máximo de 100 caracteres.
    - **idade_padrao**, **idade_minima**, **idade_maxima**: Idades de referência para a série.
        - **Validação:** Obrigatório, Número inteiro.
    - **bloquear_idade_fora_do_limite**: Bloqueia matrícula de alunos com idade fora do limite.
        - **Validação:** Obrigatório, Booleano.
    - **alertar_idade_fora_do_limite**: Alerta sobre alunos com idade fora do limite.
        - **Validação:** Obrigatório, Booleano.
    - **carga_horaria**: Carga horária da série.
        - **Validação:** Opcional, Número inteiro.
    - **curso_id**: Relacionamento com o curso.
        - **Validação:** Obrigatório, Chave estrangeira para a coleção `curso`.

---

### **turma**
- **Descrição:** Armazena as turmas.
- **Campos:**
    - **id**: Identificador único (UUID).
        - **Validação:** Obrigatório, Único.
    - **nome**: Nome da turma.
        - **Validação:** Obrigatório, String, Máximo de 100 caracteres.
    - **abreviacao**: Abreviação do nome da turma.
        - **Validação:** Opcional, String, Máximo de 6 caracteres.
    - **codigo_inep**: Código INEP da turma.
        - **Validação:** Opcional, String, Máximo de 15 dígitos numéricos.
    - **sala**: Sala da turma.
        - **Validação:** Opcional, String, Máximo de 100 caracteres.
    - **ano**: Ano letivo da turma.
        - **Validação:** Obrigatório, Número inteiro (mínimo 2000).
    - **periodo**: Período da turma.
        - **Validação:** Obrigatório, String, Seleção entre as opções 'Manhã', 'Tarde', 'Noite', 'Integral'.
    - **estudantes_max**, **estudantes_excesso**, **estudantes_pcd**: Limites de estudantes na turma.
        - **Validação:** Obrigatório, Número inteiro.
    - **dias_da_semana**: Dias em que a turma tem aula.
        - **Validação:** Obrigatório, JSON, Menu suspenso (múltiplo).
    - **multiseriado**, **lista_alternativa_disciplinas**: Indicadores de características da turma.
        - **Validação:** Opcional, Booleano.
    - **escola_id**, **serie_id**: Chaves estrangeiras obrigatórias para `escola` e `serie`.

---

# Dicionário de Dados - Schema Educacional (Continuação)

---

### **conteudo_bncc**
- **Descrição:** Tabela de junção que relaciona Conteúdos com suas respectivas competências da BNCC.
- **Campos:**
    - **id**: Identificador único (Integer).
        - **Validação:** Obrigatório, Autoincremento, Único.
    - **conteudo_id**: Relacionamento com o conteúdo.
        - **Validação:** Opcional, Chave estrangeira para a coleção `conteudo`. 
    - **bncc_id**: Relacionamento com a competência da BNCC.
        - **Validação:** Opcional, Chave estrangeira para a coleção `bncc`. 

---

### **conteudo_disciplina**
- **Descrição:** Tabela de junção que relaciona um Conteúdo a uma Disciplina.
- **Campos:**
    - **id**: Identificador único (Integer).
        - **Validação:** Obrigatório, Autoincremento, Único.
    - **conteudo_id**: Relacionamento com o conteúdo.
        - **Validação:** Opcional, Chave estrangeira para a coleção `conteudo`. 
    - **disciplina_id**: Relacionamento com a disciplina.
        - **Validação:** Opcional, Chave estrangeira para a coleção `disciplina`. 

---

### **curso_escola**
- **Descrição:** Tabela de junção que relaciona Cursos com Escolas.
- **Campos:**
    - **id**: Identificador único (Integer).
        - **Validação:** Obrigatório, Autoincremento, Único.
    - **curso_id**: Relacionamento com o curso.
        - **Validação:** Opcional, Chave estrangeira para a coleção `curso`. 
    - **escola_id**: Relacionamento com a escola.
        - **Validação:** Opcional, Chave estrangeira para a coleção `escola`. 

---

### **cursos_e_regras**
- **Descrição:** Agrupamento para as coleções de Cursos e Regras de Avaliação.
- **Campos:** Esta é uma coleção para agrupamento, não possui campos próprios. 

---

### **disciplinas_e_conteudos**
- **Descrição:** Agrupamento para as coleções relacionadas a Disciplinas e Conteúdos.
- **Campos:** Esta é uma coleção para agrupamento, não possui campos próprios. 

---

### **eduprime**
- **Descrição:** Pagantes do EduPrime. 
- **Campos:**
    - **id**: Identificador único (Integer).
        - **Validação:** Obrigatório, Autoincremento, Único.
    - **status**: Status do registro.
        - **Validação:** Obrigatório, String, Seleção entre as opções 'Publicado', 'Rascunho' e 'Arquivado'. 
    - **sort**: Campo para ordenação.
        - **Validação:** Opcional, Número inteiro. 
    - **name**: Nome do responsável.
        - **Validação:** Opcional, String, Máximo de 100 caracteres. 
    - **doc_id**: CNPJ ou CPF.
        - **Validação:** Obrigatório, String, Único, Indexado. 
    - **phone**: Telefone de contato.
        - **Validação:** Opcional, String, Único, Formato de telefone válido ^\\(?\\d{2}\\)?\\s?\\d{4,5}-?\\d{4}$.
    - **cidade**: Cidade.
        - **Validação:** Opcional, String, Máximo de 100 caracteres. 
    - **UF**: Unidade Federativa.
        - **Validação:** Opcional, String, Seleção entre as opções 'AC', 'AL', etc. 

---

### **escola_censo**

**Descrição:** Armazena informações complementares da escola, muitas delas relacionadas ao Censo Escolar.

**Campos:**
* **id:**
    * **Descrição:** Identificador único (UUID).
    * **Validação:** Obrigatório, Único.
* **status:**
    * **Descrição:** Status do registro para controle de versionamento e soft delete.
    * **Validação:** Obrigatório, String.
    * **Interface:** Utilização de Seleção.
    * **Opções:** `Publicado`, `Rascunho`, `Arquivado`.
* **escola_id:**
    * **Descrição:** Relacionamento com a escola.
    * **Validação:** Obrigatório, Chave estrangeira para a coleção `escola`.
* **serializacao:**
    * **Descrição:** Tipo de seriação da escola.
    * **Validação:** Opcional, String.
    * **Interface:** Utilização de Botão de seleção única.
    * **Opções:** `Anual`, `Creche`.
* **codigo_inep_escola_compartilhada:**
    * **Descrição:** Código INEP da outra escola com a qual o espaço é compartilhado.
    * **Validação:** Opcional, String, Máximo de 15 dígitos numéricos.
* **estado_operacional:**
    * **Descrição:** Indica se a escola está em funcionamento.
    * **Validação:** Opcional, Booleano.
* **situacao_proprietaria:**
    * **Descrição:** Situação de propriedade do imóvel da escola.
    * **Validação:** Opcional, Seleção.
    * **Interface:** Utilização de Botão de seleção única.
    * **Opções:** `Própria`, `Alugada`.
* **dependencia_administrativa:**
    * **Descrição:** Dependência administrativa da escola.
    * **Validação:** Opcional, Seleção.
    * **Interface:** Utilização de Seleção.
    * **Opções:** `Municipal`, `Estadual`, `Federal`, `Privada`.
* **uso_propriedade:**
    * **Descrição:** Tipo de uso da propriedade pela escola.
    * **Validação:** Opcional, Seleção.
    * **Interface:** Utilização de Botão de seleção única.
    * **Opções:** `Exclusiva`, `Compartilhada`.
* **escola_compartilhada:**
    * **Descrição:** Indica se o prédio é compartilhado com outra escola.
    * **Validação:** Opcional, Booleano.
* **tratamento_lixo:**
    * **Descrição:** Formas de tratamento do lixo utilizadas pela escola.
    * **Validação:** Opcional, Seleção.
    * **Interface:** Utilização de Seleção.
    * **Opções:** `Incineração`, `Aterro`, `Compostagem`, `Reciclagem`, `Outro`.
* **salas_uso_geral:**
    * **Descrição:** Espaços de uso geral disponíveis na escola.
    * **Validação:** Opcional, JSON.
    * **Interface:** Utilização de Menu suspenso (Múltiplo).
    * **Opções:** `Sala de aula`, `Auditório`, `Espaços comuns`, `Almoxarifado`, `Biblioteca`, `Sala de professores`, `Banheiro`, `Banheiro acessível`, `Banheiro de professores`, `Cozinha`, `Dormitório de alunos`, `Dormitório de professores`, `Piscina`, `Refeitório`, `Pátio aberto`, `Pátio fechado`, `Quadra coberta`, `Quadra descoberta`, `Secretaria`, `Estacionamento`, `Cantina`.
* **laboratorios:**
    * **Descrição:** Laboratórios disponíveis na escola.
    * **Validação:** Opcional, JSON.
    * **Interface:** Utilização de Menu suspenso (Múltiplo).
    * **Opções:** `Informática`, `Ciências`, `Multimídia`.
* **tipos_conexao:**
    * **Descrição:** Tipos de conexão com a internet disponíveis.
    * **Validação:** Opcional, JSON.
    * **Interface:** Utilização de Menu suspenso (Múltiplo).
    * **Opções:** `Fibra ótica`, `Banda larga`, `Satélite`, `Outro`.
* **dispositivos_usados_estudantes:**
    * **Descrição:** Dispositivos eletrônicos disponíveis para uso dos estudantes.
    * **Validação:** Opcional, JSON.
    * **Interface:** Utilização de Menu suspenso (Múltiplo).
    * **Opções:** `Computador`, `Tablet`, `Smartphone`.
* **equipamentos_ensino:**
    * **Descrição:** Equipamentos de auxílio ao ensino disponíveis.
    * **Validação:** Opcional, JSON.
    * **Interface:** Utilização de Menu suspenso (Múltiplo).
    * **Opções:** `Projetor`, `DVD/Blu-ray`, `TV multimídia`, `Lousa digital`, `Sistema de som`.
* **corpos_colegiados:**
    * **Descrição:** Órgãos colegiados em funcionamento na escola.
    * **Validação:** Opcional, JSON.
    * **Interface:** Utilização de Menu suspenso (Múltiplo).
    * **Opções:** `Associação de Pais`, `Associação de Pais e Mestres`, `Grêmio Estudantil`, `Conselho Escolar`, `Não há órgãos colegiados`.
* **materiais_pedagogicos:**
    * **Descrição:** Materiais pedagógicos específicos disponíveis.
    * **Validação:** Opcional, JSON.
    * **Interface:** Utilização de Menu suspenso (Múltiplo).
    * **Opções:** `Arquivo multimídia`, `Brinquedos`, `Jogos educativos`, `Materiais científicos`, `Equipamentos de áudio`, `Instrumentos musicais`, `Materiais culturais/artísticos`, `Materiais de educação profissional`, `Materiais esportivos`, `Materiais educacionais indígenas`, `Materiais étnicos`, `Materiais educacionais do campo`, `Nenhum dos anteriores`.
* **criterios_selecao:**
    * **Descrição:** Critérios utilizados para a seleção de alunos.
    * **Validação:** Opcional, JSON.
    * **Interface:** Utilização de Menu suspenso (Múltiplo).
    * **Opções:** `Análise curricular`, `Exame de seleção`, `Cotas`.
* **linguagens_indigenas_disponiveis:**
    * **Descrição:** Línguas indígenas ensinadas na escola.
    * **Validação:** Opcional, JSON.
    * **Interface:** Utilização de Menu suspenso (Múltiplo).
    * **Opções:** `Português`, `Ticuna`, `Guarani Kaiowá`, `Kaingang`, `Xavante`, `Yanomami`, `Outro`.
* **salas_internas, salas_externas, salas_refrigeradas, salas_acessiveis:**
    * **Descrição:** Quantidade de salas por tipo.
    * **Validação:** Opcional, Número inteiro (mínimo 0).
* **desktops_disponiveis, laptops_disponiveis, tablets_disponiveis:**
    * **Descrição:** Quantidade de dispositivos por tipo.
    * **Validação:** Opcional, Número inteiro (mínimo 0).
* **pessoal_administrativo, pessoal_ensino, pessoal_servicos_gerais, pessoal_seguranca, pessoal_gestao, pessoal_saude, pessoal_assistencia_social:**
    * **Descrição:** Quantidade de pessoal por função.
    * **Validação:** Opcional, Número inteiro (mínimo 0).
* **demais campos booleanos:** `tem_agua_potavel`, `tem_tratamento_esgoto`, `tem_eletricidade`, `esgoto_tratado_pela_escola`, `tem_servico_alimentacao`, `usa_espacos_externos`, `tem_espacos_comunitarios`, `localizacao_incomum`, `usa_regras_alternativas`, `faz_parte_de_rede`, `tem_internet`, `tem_rede_local`, `tem_assistencia_especializada`, `projeto_pedagogico_atualizado`, `tem_educacao_indigena`, `ligada_educacao_superior`.
    * **Validação:** Opcional, Booleano.

---

### **escola_professor**

**Descrição:** Tabela de junção que relaciona Escolas com Professores.

**Campos:**
* **id:**
    * **Descrição:** Identificador único (Integer).
    * **Validação:** Obrigatório, Autoincremento, Único.
* **escola_id:**
    * **Descrição:** Relacionamento com a escola.
    * **Validação:** Obrigatório, Chave estrangeira para a coleção `escola`.
* **professor_id:**
    * **Descrição:** Relacionamento com o professor.
    * **Validação:** Obrigatório, Chave estrangeira para a coleção `professor`.
* **status:**
    * **Descrição:** Status do registro para controle de versionamento e soft delete.
    * **Validação:** Obrigatório, String.
    * **Interface:** Utilização de Seleção.
    * **Opções:** `Publicado`, `Rascunho`, `Arquivado`.

---

### **etapa**

**Descrição:** Armazena as etapas (bimestres, trimestres, etc.) de um ano letivo.

**Campos:**
* **id:**
    * **Descrição:** Identificador único (UUID).
    * **Validação:** Obrigatório, Único.
* **status:**
    * **Descrição:** Status do registro para controle de versionamento e soft delete.
    * **Validação:** Obrigatório, String.
    * **Interface:** Utilização de Seleção.
    * **Opções:** `Publicado`, `Rascunho`, `Arquivado`.
* **numero_etapa:**
    * **Descrição:** Número da etapa.
    * **Validação:** Obrigatório, Número inteiro (de 1 a 100).
* **data_de_inicio:**
    * **Descrição:** Data de início da etapa.
    * **Validação:** Obrigatório, Data e Hora.
* **data_do_fim:**
    * **Descrição:** Data de término da etapa.
    * **Validação:** Obrigatório, Data e Hora.
* **instituicao_id:**
    * **Descrição:** Relacionamento com a instituição.
    * **Validação:** Obrigatório, Chave estrangeira para a coleção `instituicao`.

---

### **feedback_aluno**

**Descrição:** Armazena feedbacks (pareceres descritivos) sobre os alunos.

**Campos:**
* **id:**
    * **Descrição:** Identificador único (UUID).
    * **Validação:** Obrigatório, Único.
* **status:**
    * **Descrição:** Status do registro para controle de versionamento e soft delete.
    * **Validação:** Obrigatório, String.
    * **Interface:** Utilização de Seleção.
    * **Opções:** `Publicado`, `Rascunho`, `Arquivado`.
* **aluno_id:**
    * **Descrição:** Chave estrangeira obrigatória para `aluno`.
* **matricula_id:**
    * **Descrição:** Chave estrangeira obrigatória para `matricula`.
* **escola_id:**
    * **Descrição:** Chave estrangeira obrigatória para `escola`.
* **disciplina_id:**
    * **Descrição:** Chave estrangeira obrigatória para `disciplina`.
* **professor_id:**
    * **Descrição:** Chave estrangeira obrigatória para `professor`.
* **feedback_inicial:**
    * **Descrição:** Parecer descritivo inicial.
    * **Validação:** Opcional, Texto (máximo 1000 caracteres).
* **feedback_parcial:**
    * **Descrição:** Parecer descritivo parcial.
    * **Validação:** Opcional, Texto (máximo 1000 caracteres).
* **feedback_final:**
    * **Descrição:** Parecer descritivo final.
    * **Validação:** Opcional, Texto (máximo 1000 caracteres).
* **inicial_criacao, parcial_criacao, final_criacao:**
    * **Descrição:** Datas de criação de cada parecer.
    * **Validação:** Opcional, Data e Hora.
* **inicial_atualizacao, parcial_atualizacao, final_atualizacao:**
    * **Descrição:** Datas da última atualização de cada parecer.
    * **Validação:** Opcional, Data e Hora.

---

### **frequencias**

**Descrição:** Agrupamento para as coleções relacionadas a Frequência.

**Campos:** Esta é uma coleção para agrupamento, não possui campos próprios.

---

### **funcao_servidor**

**Descrição:** Armazena as possíveis funções para um servidor (funcionário).

**Campos:**
* **id:**
    * **Descrição:** Identificador único (UUID).
    * **Validação:** Obrigatório, Único.
* **status:**
    * **Descrição:** Status do registro para controle de versionamento e soft delete.
    * **Validação:** Obrigatório, String.
    * **Interface:** Utilização de Seleção.
    * **Opções:** `Publicado`, `Rascunho`, `Arquivado`.
* **nome:**
    * **Descrição:** Nome da função.
    * **Validação:** Obrigatório, String, Mínimo 3 e máximo 100 caracteres.
* **abreviacao:**
    * **Descrição:** Abreviação do nome da função.
    * **Validação:** Opcional, String, Máximo de 6 caracteres.
* **descricao:**
    * **Descrição:** Descrição da função.
    * **Validação:** Opcional, Texto, Máximo de 255 caracteres.

---

### **horarios**

**Descrição:** Armazena os horários das aulas.

**Campos:**
* **id:**
    * **Descrição:** Identificador único (UUID).
    * **Validação:** Obrigatório, Único.
* **status:**
    * **Descrição:** Status do registro para controle de versionamento e soft delete.
    * **Validação:** Obrigatório, String.
    * **Interface:** Utilização de Seleção.
    * **Opções:** `Publicado`, `Rascunho`, `Arquivado`.
* **dias_da_semana:**
    * **Descrição:** Dia da semana da aula.
    * **Validação:** Obrigatório, JSON.
    * **Interface:** Utilização de Menu suspenso (Múltiplo).
    * **Opções:** `MONDAY`, `TUESDAY`, `WEDNESDAY`, `THURSDAY`, `FRIDAY`, `SATURDAY`, `SUNDAY`.
* **inicio:**
    * **Descrição:** Horário de início da aula.
    * **Validação:** Obrigatório, Data e Hora.
* **fim:**
    * **Descrição:** Horário de término da aula.
    * **Validação:** Obrigatório, Data e Hora.
* **turma_id:**
    * **Descrição:** Chave estrangeira obrigatória para `turma`.
* **escola_id:**
    * **Descrição:** Chave estrangeira obrigatória para `escola`.
* **disciplina_id:**
    * **Descrição:** Chave estrangeira obrigatória para `disciplina`.

---

### **instituicao**

**Descrição:** Armazena informações sobre as instituições (redes de ensino).

**Campos:**
* **id:**
    * **Descrição:** Identificador único (UUID).
    * **Validação:** Obrigatório, Único.
* **status:**
    * **Descrição:** Status do registro para controle de versionamento e soft delete.
    * **Validação:** Obrigatório, String.
    * **Interface:** Utilização de Seleção.
    * **Opções:** `Publicado`, `Rascunho`, `Arquivado`.
* **nome:**
    * **Descrição:** Nome da instituição.
    * **Validação:** Obrigatório, String, Mínimo 3 e máximo 100 caracteres.
* **responsavel:**
    * **Descrição:** Usuário responsável pela instituição.
    * **Validação:** Obrigatório, Chave estrangeira para a coleção `directus_users`.
* **eduprime_id:**
    * **Descrição:** Relacionamento com a licença EduPrime.
    * **Validação:** Obrigatório, Chave estrangeira para a coleção `eduprime`.
* **telefone:**
    * **Descrição:** Telefone da instituição.
    * **Validação:** Opcional, String, Exatamente 11 dígitos numéricos.
* **email:**
    * **Descrição:** Email da instituição.
    * **Validação:** Opcional, String, Formato de e-mail válido.
* **cep:**
    * **Descrição:** CEP da instituição.
    * **Validação:** Opcional, String, Exatamente 8 dígitos numéricos.
* **endereco, cidade, estado:**
    * **Descrição:** Dados de localização da instituição.
    * **Validação:** Opcional, String.

---

### **justificativa**

**Descrição:** Armazena tipos de justificativa para ausências.

**Campos:**
* **id:**
    * **Descrição:** Identificador único (UUID).
    * **Validação:** Obrigatório, Único.
* **status:**
    * **Descrição:** Status do registro para controle de versionamento e soft delete.
    * **Validação:** Obrigatório, String.
    * **Interface:** Utilização de Seleção.
    * **Opções:** `Publicado`, `Rascunho`, `Arquivado`.
* **nome:**
    * **Descrição:** Nome/descrição da justificativa.
    * **Validação:** Obrigatório, String, Mínimo 3 e máximo 100 caracteres.

---

### **matriculas**

**Descrição:** Agrupamento para as coleções de Matrículas.

**Campos:** Esta é uma coleção para agrupamento, não possui campos próprios.

---

### **numero_faltas**

**Descrição:** Armazena o registro de uma falta individual de um aluno em uma aula.

**Campos:**
* **id:**
    * **Descrição:** Identificador único (UUID).
    * **Validação:** Obrigatório, Único.
* **status:**
    * **Descrição:** Status do registro para controle de versionamento e soft delete.
    * **Validação:** Obrigatório, String.
    * **Interface:** Utilização de Seleção.
    * **Opções:** `Publicado`, `Rascunho`, `Arquivado`.
* **nome:**
    * **Descrição:** Nome/descrição do registro de falta (gerado automaticamente).
    * **Validação:** Obrigatório, String, Mínimo 3 e máximo 100 caracteres.
* **ausente:**
    * **Descrição:** Indica se o aluno esteve ausente.
    * **Validação:** Obrigatório, Booleano.
* **frequencia_id:**
    * **Descrição:** Relacionamento com o registro de frequência da aula.
    * **Validação:** Obrigatório, Chave estrangeira para a coleção `frequencia`.

---

### **pessoa_autorizada**
- **Descrição:** Armazena pessoas autorizadas a buscar um aluno.
- **Campos:**
    - **id**: Identificador único (UUID).
        - **Validação:** Obrigatório, Único.
    - **nome**: Nome da pessoa autorizada.
        - **Validação:** Obrigatório, Texto, Mínimo de 3, Máximo de 100 caracteres. 
    - **parentesco**: Grau de parentesco com o aluno.
        - **Validação:** Obrigatório, Texto, Mínimo de 3, Máximo de 20 caracteres. 
    - **telefone**: Telefone da pessoa autorizada.
        - **Validação:** Obrigatório, Texto, Exatos 11 dígitos. 
    - **email**: Email da pessoa autorizada.
        - **Validação:** Opcional, Texto, Máximo de 100 caracteres, Regex de ^[\w\.-]+@[\w\.-]+\.\w{2,}$ . 
    - **aluno_id**: Relacionamento com o aluno.
        - **Validação:** Obrigatório, Chave estrangeira para a coleção `aluno`. 

---

### **pessoas**
- **Descrição:** Agrupamento para coleções relacionadas a pessoas (alunos, professores, etc.).
- **Campos:** Esta é uma coleção para agrupamento, não possui campos próprios. 

---

### **pre_matricula**
- **Descrição:** Armazena os registros de pré-matrícula dos alunos.
- **Campos:**
    - **id**: Identificador único (UUID).
        - **Validação:** Obrigatório, Único.
    - **codigo_pre_matricula**: Código identificador da pré-matrícula.
        - **Validação:** Opcional, Único, Texto, Máximo de 100 caracteres. 
    - **data_pre_matricula**: Data da realização da pré-matrícula.
        - **Validação:** Obrigatório, Data e Hora. 
    - **periodo**: Período desejado.
        - **Validação:** Obrigatório, Seleção entre 'Manhã', 'Tarde', 'Noite', 'Integral'. 
    - **escola_id**, **aluno_id**, **curso_id**, **series_id**, **instituicao_id**: Chaves estrangeiras obrigatórias para `escola`, `aluno`, `curso`, e `serie`. 

---

### **professor_disciplina**
- **Descrição:** Tabela de junção que relaciona Professores com as Disciplinas que lecionam.
- **Campos:**
    - **id**: Identificador único (Integer).
        - **Validação:** Obrigatório, Autoincremento, Único.
    - **carga_horaria**: Carga horária do professor para aquela disciplina.
        - **Validação:** Obrigatório, Número inteiro. 
    - **professor_id**: Relacionamento com o professor.
        - **Validação:** Obrigatório, Chave estrangeira para a coleção `professor`. 
    - **disciplina_id**: Relacionamento com a disciplina.
        - **Validação:** Obrigatório, Chave estrangeira para a coleção `disciplina`. 

---

### **serie_disciplina**
- **Descrição:** Tabela de junção que relaciona Séries com suas respectivas Disciplinas.
- **Campos:**
    - **id**: Identificador único (Integer).
        - **Validação:** Obrigatório, Autoincremento, Único.
    - **carga_horaria**: Carga horária da disciplina para aquela série.
        - **Validação:** Obrigatório, Número inteiro. 
    - **serie_id**: Relacionamento com a série.
        - **Validação:** Obrigatório, Chave estrangeira para a coleção `serie`. 
    - **disciplina_id**: Relacionamento com a disciplina.
        - **Validação:** Obrigatório, Chave estrangeira para a coleção `disciplina`. 

---

### **series_e_turmas**
- **Descrição:** Agrupamento para as coleções de Séries e Turmas.
- **Campos:** Esta é uma coleção para agrupamento, não possui campos próprios. 

---

### **servidor**
- **Descrição:** Armazena informações sobre os servidores (funcionários) da instituição.
- **Campos:**
    - **id**: Identificador único (UUID).
        - **Validação:** Obrigatório, Único.
    - **nome**: Nome do servidor.
        - **Validação:** Obrigatório, Texto, Mínimo de 3, Máximo de 100 caracteres. 
    - **cpf**: CPF do servidor.
        - **Validação:** Obrigatório, Único, Texto, Exatamente 11 dígitos. 
    - **data_de_nascimento**: Data de nascimento do servidor.
        - **Validação:** Obrigatório, Data. 
    - **escola_id**, **instituicao_id**: Chaves estrangeiras obrigatórias para `escola` e `instituicao`. 
    - **funcao_servidor_id**: Relacionamento com a função do servidor.
        - **Validação:** Obrigatório, Chave estrangeira para `funcao_servidor`. 
    - **email**: E-mail do servidor.
        - **Validação:** Opcional, Texto, Máximo de 255 caracteres, Regex de ^[\w\.-]+@[\w\.-]+\.\w{2,}$
    - **telefone**: Telefone do servidor.
        - **Validação:** Opcional, Texto, Exatamente 11 dígitos. 
    - **endereco**: Endereço do servidor.
        - **Validação:** Opcional, Texto, Máximo de 255 caracteres. 
    - **tipo_contrato**: Tipo de contrato do servidor.
        - **Validação:** Opcional, Seleção de opções como 'Indeterminado', 'Contratado', etc.. 
    - **escolaridade**: Nível de escolaridade do servidor.
        - **Validação:** Opcional, Seleção de opções como 'Fundamental incompleto', 'Superior completo', etc.. 

---

### **turma_disciplina**
- **Descrição:** Tabela de junção que relaciona Turmas com suas Disciplinas.
- **Campos:**
    - **id**: Identificador único (Integer).
        - **Validação:** Obrigatório, Autoincremento, Único.
    - **carga_horaria**: Carga horária da disciplina para aquela turma.
        - **Validação:** Obrigatório, Número inteiro. 
    - **turma_id**: Relacionamento com a turma.
        - **Validação:** Obrigatório, Chave estrangeira para a coleção `turma`. 
    - **disciplina_id**: Relacionamento com a disciplina.
        - **Validação:** Obrigatório, Chave estrangeira para a coleção `disciplina`. 

---

### **unidade_tematica**
- **Descrição:** Armazena as unidades temáticas de uma disciplina/série.
- **Campos:**
    - **id**: Identificador único (UUID).
        - **Validação:** Obrigatório, Único.
    - **nome**: Nome da unidade temática.
        - **Validação:** Obrigatório, Texto, mínimo 3 caracteres. 
    - **serie_id**: Relacionamento com a série.
        - **Validação:** Obrigatório, Chave estrangeira para a coleção `serie`. 
    - **disciplina_id**: Relacionamento com a disciplina.
        - **Validação:** Obrigatório, Chave estrangeira para a coleção `disciplina`. 

---

# Dicionário de Dados - Schema Educacional (Tabelas Adicionais)

---

### **frequencia_aluno**
- **Descrição:** Armazena dados de frequência por aluno, vinculados a uma matrícula específica.
- **Campos:**
    - **id**: Identificador único (UUID). 
        - **Validação:** Obrigatório, Único. 
    - **matricula_id**: Relacionamento com a matrícula do aluno. 
        - **Validação:** Obrigatório, Chave estrangeira para a coleção `matricula`. 
    - **tipo_falta**: Tipo de falta registrada. 
        - **Validação:** Obrigatório, Número inteiro (mínimo 0). 
    - **escola_id**: Relacionamento com a escola. 
        - **Validação:** Obrigatório, Chave estrangeira para a coleção `escola`. 

---

### **frequencia_disciplina**
- **Descrição:** Registra o total de faltas de um aluno em uma disciplina específica por etapa.
- **Campos:**
    - **id**: Identificador único (UUID). 
        - **Validação:** Obrigatório, Único. 
    - **aluno_id**: Relacionamento com o aluno. 
        - **Validação:** Obrigatório, Chave estrangeira para a coleção `aluno`. 
    - **disciplina_id**: Relacionamento com a disciplina. 
        - **Validação:** Obrigatório, Chave estrangeira para a coleção `disciplina`. 
    - **numero_faltas**: Quantidade de faltas. 
        - **Validação:** Obrigatório, Número inteiro (mínimo 0). 
    - **etapa_id**: Relacionamento com a etapa. 
        - **Validação:** Obrigatório, Chave estrangeira para a coleção `etapa`. 
    - **escola_id**: Relacionamento com a escola. 
        - **Validação:** Obrigatório, Chave estrangeira para a coleção `escola`. 

---

### **frequencia_geral**
- **Descrição:** Armazena o registro geral de faltas de um aluno por etapa.
- **Campos:**
    - **id**: Identificador único (UUID). 
        - **Validação:** Obrigatório, Único. 
    - **numero_faltas**: Quantidade total de faltas na etapa. 
        - **Validação:** Obrigatório, Número inteiro (de 1 a 100). 
    - **aluno_id**: Relacionamento com o aluno. 
        - **Validação:** Obrigatório, Chave estrangeira para a coleção `aluno`. 
    - **etapa_id**: Relacionamento com a etapa. 
        - **Validação:** Obrigatório, Chave estrangeira para a coleção `etapa`. 
    - **escola_id**: Relacionamento com a escola. 
        - **Validação:** Obrigatório, Chave estrangeira para a coleção `escola`. 

---

### **frequencia_professor**
- **Descrição:** Registra a frequência de aulas dadas por um professor.
- **Campos:**
    - **id**: Identificador único (UUID). 
        - **Validação:** Obrigatório, Único. 
    - **data**: Data do registro. 
        - **Validação:** Obrigatório, Data e Hora. 
    - **total_aulas**: Total de aulas no dia/disciplina. 
        - **Validação:** Obrigatório, Número inteiro (mínimo 0). 
    - **tipo_frequencia**: Tipo de frequência registrada. 
        - **Validação:** Obrigatório, Seleção entre 'Diária' e 'Disciplinar'. 
    - **professor_id**, **turma_id**, **etapa_id**, **escola_id**: Chaves estrangeiras obrigatórias para `professor`, `turma`, `etapa` e `escola`. 
    - **disciplina_id**: Relacionamento com a disciplina (opcional). 
        - **Validação:** Opcional, Chave estrangeira para `disciplina`. 


---

### **instituicao_directus_users**
- **Descrição:** Tabela de junção que relaciona usuários do sistema (`directus_users`) com as Instituições às quais eles pertencem.
- **Campos:**
    - **id**: Identificador único (Integer). 
        - **Validação:** Obrigatório, Autoincremento, Único. 
    - **instituicao_id**: Relacionamento com a instituição. 
        - **Validação:** Obrigatório, Chave estrangeira para a coleção `instituicao`. 
    - **directus_users_id**: Relacionamento com o usuário. 
        - **Validação:** Obrigatório, Chave estrangeira para a coleção `directus_users`. 

---

### **instituicoes_e_pessoas**
- **Descrição:** Agrupamento para as coleções de Instituições e Pessoas.
- **Campos:** Esta é uma coleção para agrupamento, não possui campos próprios.

---

### **nota_conceitual**
- **Descrição:** Armazena as notas conceituais dos alunos por disciplina e etapa.
- **Campos:**
    - **id**: Identificador único (UUID). 
        - **Validação:** Obrigatório, Único. 
    - **aluno_id**, **matricula_id**, **turma_id**, **disciplina_id**, **escola_id**, **etapa_id**: Chaves estrangeiras obrigatórias para `aluno`, `matricula`, `turma`, `disciplina`, `escola` e `etapa`. 

---

### **nota_conceitual_unidade_tematica**
- **Descrição:** Detalha a nota conceitual para uma unidade temática específica.
- **Campos:**
    - **id**: Identificador único (UUID). 
        - **Validação:** Obrigatório, Único. 
    - **nota**: Nota conceitual atribuída. 
        - **Validação:** Obrigatório, Seleção, Opções entre PC, PEC, PNC e NT. 
    - **unidade_tematica_id**: Relacionamento com a unidade temática. 
        - **Validação:** Obrigatório, Chave estrangeira para a coleção `unidade_tematica`. 
    - **nota_conceitual_id**: Relacionamento com o registro principal de nota conceitual. 
        - **Validação:** Obrigatório, Chave estrangeira para a coleção `nota_conceitual`. 

---

### **nota_disciplina**
- **Descrição:** Armazena as notas de atividades de um aluno em uma disciplina por etapa.
- **Campos:**
    - **id**: Identificador único (UUID). 
        - **Validação:** Obrigatório, Único. 
    - **at1**, **at2**, **at3**, **at4**, **avg**: Notas das atividades e média. 
        - **Validação:** Obrigatório, Número inteiro (mínimo 0). 
    - **aluno_id**, **matricula_id**, **escola_id**, **etapa_id**: Chaves estrangeiras obrigatórias para `aluno`, `matricula`, `escola` e `etapa`. 
    - **disciplina_id**: Relacionamento com a disciplina. 
        - **Validação:** Opcional, Chave estrangeira para a coleção `disciplina`. 

---

### **nota_geral**
- **Descrição:** Armazena a nota geral de um aluno por etapa.
- **Campos:**
    - **id**: Identificador único (UUID). 
        - **Validação:** Obrigatório, Único. 
    - **nota**: Nota geral. 
        - **Validação:** Obrigatório, Número inteiro (mínimo 0). 
    - **nota_arredondada**: Nota geral após arredondamento. 
        - **Validação:** Opcional, Número inteiro (mínimo 0). 
    - **aluno_id**, **escola_id**, **etapa_id**: Chaves estrangeiras obrigatórias para `aluno`, `escola` e `etapa`. 

---

### **nota_numerica**
- **Descrição:** Armazena as notas numéricas de atividades e recuperação.
- **Campos:**
    - **id**: Identificador único (UUID). 
        - **Validação:** Obrigatório, Único. 
    - **at1**, **at2**, **at3**, **at4**, **at5**, **recuperacao**, **nota**: Notas de atividades, recuperação e final. 
        - **Validação:** Opcional, Número inteiro (mínimo 0). 
    - **aluno_id**, **matricula_id**, **disciplina_id**, **etapa_id**, **escola_id**: Chaves estrangeiras obrigatórias para `aluno`, `matricula`, `disciplina`, `etapa` e `escola`. 

---

### **nota_registrada**
- **Descrição:** Controla a liberação de notas por turma e disciplina.
- **Campos:**
    - **id**: Identificador único (UUID). 
        - **Validação:** Obrigatório, Único. 
    - **notas_liberadas**: Indica se as notas foram liberadas para consulta. 
        - **Validação:** Obrigatório, Booleano. 
    - **completo**: Indica se o registro de notas para a etapa/disciplina está completo. 
        - **Validação:** Obrigatório, Booleano. 
    - **professor_id**, **turma_id**, **disciplina_id**, **etapa_id**: Chaves estrangeiras obrigatórias para `professor`, `turma`, `disciplina` e `etapa`.
*Observação: As tabelas/coleções que não possuem campos próprios (como `cursos_e_regras`, `disciplinas_e_conteudos`, etc.) servem apenas como agrupadores visuais na interface do Directus e não representam tabelas físicas com dados.*

*Nota: As tabelas `nota_conceitual`, `nota_conceitual_unidade_tematica`, `nota_disciplina`, `nota_geral` e `nota_numerica` foram omitidas por terem uma estrutura muito similar e repetitiva, focada em registrar diferentes tipos de notas com chaves estrangeiras para `aluno`, `matricula`, `escola`, `disciplina` e `etapa`.*

*Observação: Campos como `user_created`, `date_created`, `user_updated`, e `date_updated` são de sistema, preenchidos automaticamente e não foram detalhados.*
