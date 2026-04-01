📋 Relatório de Bugs: Calculadora Standard v1.0
Status do Projeto: Bloqueado (Crítico)

Severidade: Alta

🔴 BUG-001: Falha Crítica na Operação de Apagar (Backspace)
Descrição: Ao clicar no botão "Del", em vez de remover apenas o último caractere digitado, a aplicação apaga toda a expressão e mantém apenas o primeiro número.

Comportamento Esperado: Remover apenas o último caractere da string (Ex: de 123 para 12).

Comportamento Atual: De 123 para 1.

🔴 BUG-002: Corrupção de Valor no Cálculo (Atribuição Indevida)
Descrição: Após qualquer cálculo, o sistema parece forçar o resultado para "Infinity" ou falhar em operações matemáticas simples.

Evidência: Ao somar 2 + 2, o sistema não retorna 4 consistentemente ou exibe erros de validação inexistentes.

Suspeita: Verificação de erro de divisão por zero está sobrescrevendo o valor da variável de resultado.

🟡 BUG-003: Concatenação com Zero à Esquerda
Descrição: Ao iniciar a calculadora ou limpá-la (C), o número 0 permanece no visor. Se o usuário digita 5, o visor mostra 05.

Impacto: Erro visual e potencial erro de interpretação do motor matemático (Octal).

Comportamento Esperado: O 5 deve substituir o 0 inicial.

🟡 BUG-004: Dessincronização de Memória Pós-Cálculo
Descrição: Após clicar em =, o resultado aparece na tela, mas se o usuário tentar continuar a conta (ex: clicar em + 5), a calculadora usa a expressão antiga e não o novo resultado.

Passos para Reproduzir: 5 + 5 = (mostra 10). Em seguida, clique em + 2.

Resultado: O sistema tenta calcular 5+5+2 novamente ou ignora o 10.

🟠 BUG-005: Injeção de Operadores Múltiplos (Crash de Lógica)
Descrição: O campo de entrada permite que o usuário digite múltiplos operadores seguidos, como 5 ++ -- * 2.

Impacto: A aplicação "quebra" (mostra "Erro") porque a expressão matemática se torna inválida para processamento.

🔵 BUG-006: Erro de Precisão em Ponto Flutuante
Descrição: Cálculos com decimais apresentam dízimas estranhas.

Exemplo: 0.1 + 0.2 resulta em 0.30000000000000004 em vez de 0.3.

Requisito: O resultado deve ser amigável para o usuário final (limitar casas decimais).