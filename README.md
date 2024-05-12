# GooAluraNoChurn
AI project focus on stop churn on Telecom Fale Bem Company \n
Arquivo Projeto Python chatBot_Churn.ipynb

Aplicação com o objetivo de retenção de clientes de telefonia para evitar processo de churn(migração de clientes entre operadoras)
Construção de Chat Bot utilizando Gemini 1.5 e aplicação Salesforce desenvolvida em ambiente trial

# Bibliotecas utilizadas
google-generativeai
simple-salesforce
pandas

# Chaves de conexões utilizadas
GOOGLE_API_KEY = ""
SFDC_INTEGRATION_USER= "ptandreo-lgxk@force.com"
SFDC_INTEGRATION_PASS= "@1Candidato"
SFDC_INTEGRATION_TOKEN= "xUvUe9D6j7PDAC05sYYtfuFIf" #Instância nova criada em Salesforce, sem dados sensíveis e expira em 30 dias
#cpf = "972.237.264-58" #número fake de cpf para teste com dados e probabilidade de churn

# Processos de Negócio
class ChurnCalculator:
    Critério para definição de Churn
        Busca dados do cliente no Salesforce, incluindo Cases, data do primeiro contrato
        e média das faturas.        
        # Calcula a data de 30 dias atrás
        # Busca Cases
        # Busca data do primeiro contrato
        # Busca média das faturas
        
    
    def calcular_risco_churn(cases, data_primeiro_contrato, media_faturas):
        """
        Calcula o risco de churn usando média ponderada dos fatores:
        quantidade de Cases, tempo de relacionamento e média das faturas.

        # Calcula tempo de relacionamento em meses
        # Define pesos para cada fator (ajuste conforme necessário)
        peso_cases = 0.5
        peso_tempo_relacionamento = 0.3
        peso_media_faturas = 0.2

        # Calcula os scores para cada fator (ajuste as faixas conforme necessário)
        score_cases = len(cases) * 10
        score_tempo_relacionamento = max(0, 10 - tempo_relacionamento_meses) # Quanto mais tempo, menor o score
        score_media_faturas = media_faturas / 100  # Score aumenta com a média das faturas

        # Calcula a média ponderada
        risco_churn = (
            (score_cases * peso_cases) +
            (score_tempo_relacionamento * peso_tempo_relacionamento) +
            (score_media_faturas * peso_media_faturas)
        )

    

# Interação com o modelo de linguagem com base no risco de churn
if risco_churn > 0:
    prompt_churn_risk = f"O cliente {nome_cliente} dado falhas de nossos produtos ou atendimento esta em risco de churn. Seja criativo em uma resposta ou promoção de produtos de linha móvel para uma saudação e rete-lo, em nome da Empresa Fale Bem Telefonia."
    response = chat.send_message(prompt_churn_risk)

