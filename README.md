Automação para ligar e desligar instâncias EC2 usando AWS Lambda e EventBridge.

Este projeto configura uma função Lambda que, combinada com regras do EventBridge, automatiza o processo de ligar ou desligar instâncias EC2 em horários pré-determinados. Essa solução é ideal para economizar custos em ambientes de desenvolvimento ou teste.

Arquitetura
AWS Lambda: Executa o código que liga/desliga as instâncias EC2.
AWS EventBridge: Define regras de agendamento para acionar a função Lambda.
Pré-requisitos
Conta AWS ativa.
Permissões adequadas para criar funções Lambda, configurar EventBridge e gerenciar EC2.
AWS CLI configurada (opcional, mas recomendada).
Python 3.8 ou superior para editar e personalizar o código localmente.
Passos para Configuração
1. Clonar o Repositório
bash
Copiar código
git clone https://github.com/seu-usuario/func_lambda_liga_desliga_ec2.git  
cd func_lambda_liga_desliga_ec2  
2. Configurar o Código Lambda
No arquivo lambda_function.py:

Substitua INSTANCE_ID pela ID da(s) instância(s) EC2 que deseja gerenciar.
Configure a região AWS se necessário.
3. Criar a Função Lambda
Compacte o arquivo lambda_function.py em um arquivo .zip.
Faça o upload do arquivo .zip no console do AWS Lambda para criar a função.
Configure uma role com permissões para gerenciar EC2.
4. Criar Regras no EventBridge
No console do EventBridge, crie duas regras:
Regra para ligar: Define o horário para iniciar as instâncias EC2.
Regra para desligar: Define o horário para parar as instâncias EC2.
Em ambas as regras, configure o destino para acionar a função Lambda criada.
5. Testar a Configuração
No console do AWS Lambda, teste a função manualmente para garantir que as instâncias EC2 sejam ligadas e desligadas conforme esperado.
Verifique o log no CloudWatch para monitorar a execução.
Personalização
Você pode ajustar o código para:

Gerenciar múltiplas instâncias.
Ligar/desligar instâncias com base em tags.
Adicionar notificações via SNS.
Contribuições
Sinta-se à vontade para abrir issues ou pull requests para melhorar este projeto.

Licença
