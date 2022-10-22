# AWS Cloudformation CNF Outputs  

Nesse projeto foi desenvolvido um template script no foramato YML para criar sessoẽs de prática de saídas nas stacks usandp o Cloudformation da AWS.

 • Outputs (saida)
      A seção de saídas declara valores de saída que podemos
      mportar para outras stacks (para criar referências de pilha transversal)
      Ao usar stacks aninhadas, podemos ver como as saidas de uma stack aninhada são
      usada na stack raiz.
      Podemos visualizar saídas no console do CloudFormation
      Podemos declarar no máximo 60 saídas em um modelo CFN.
====================================================================================

Outputs 

• Export (Optional) 
      As exportações contêm saída de recursos usados para referência de stack cruzada.
      Para cada conta da AWS, o nome de exportação deve ser único na região.Como deve ser único,  podemos usar o nome de exportação como
      "AWS :: StackName" -ExportName
      Não podemos criar referências de stack cruzada entre regiões.
      Podemos usar a função intrínseca FN :: ImportValue para importar valores que foram exportados na mesma região.Veremos isso praticamente.
      Em termos simples, a zona de disponibilidade de exportação no Stack1 e use -a Stack2
      Para saídas, o valor da propriedade Nome de uma exportação não pode usar funções ref ou getAtt que dependem de um recurso.
      Não podemos excluir uma stack se outra stack referir uma de suas saídas.
      Não podemos modificar ou remover um valor de saída referenciado por outra stack.
      Podemos usar saídas em combinação com condições.Veremos isso em nossas sessões de prática para saídas.
========================================================================================================

Outputs Prática
      Etapa 01: Crie uma saída muito básica usando a intrinsic funtion FN :: Ref - InstanceId.
      Etapa 02: usaremos a intrinsic function FN :: GetAtt para criar saídas.
      Etapa 03: Usaremos a intrinsic function FN :: Sub intrínseca para criar saídas e usaremos o Pseudo Parâmetro AWS :: StackName.Além disso,
      Exportaremos o grupo de segurança e a zona de disponibilidade.
      Etapa 04: criaremos uma nova Stack referenciando o grupo de segurança e o valor de exportação da zona de disponibilidade da Stack anterior.
      Usaremos a intrinsic function FN :: ImportValue para importar essas exportações.
      Etapa 05: Usaremos as condições na seção de saídas para demonstrar sua combinação.
      Etapa 06: Demonstraremos FN :: Participe da funtion intrinsic.
