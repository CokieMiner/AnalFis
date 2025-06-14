# AnaFis - Análise de Dados Físicos

## Visão Geral

AnaFis é uma aplicação abrangente para análise de dados físicos com interface gráfica moderna, projetada para pesquisadores, estudantes e profissionais que trabalham com dados experimentais. A aplicação fornece ferramentas poderosas para ajuste de curvas e propagação de incertezas com capacidades de visualização em tempo real.

## Instalação

AnaFis requer Python 3.8 ou mais recente.

### Executável Pré-compilado (Windows)

Para usuários Windows, um executável autônomo está disponível que não requer instalação do Python:

1. Baixe a versão mais recente da seção de releases
2. Extraia a pasta `AnaFis` para o local desejado
3. Execute `AnaFis.exe` diretamente

O executável é portátil e inclui todas as dependências.

### Opção 1: Instalar usando setup.py (Recomendado)

Clone ou baixe o repositório e execute:

```bash
python setup.py install
```

Ou para instalação de desenvolvimento:

```bash
pip install -e .
```

### Opção 2: Instalação manual de dependências

Se você preferir instalar as dependências manualmente:

```bash
pip install numpy scipy sympy matplotlib pandas
```

**Nota:** `tkinter` vem pré-instalado com o Python e não precisa ser instalado separadamente.

## Executando a Aplicação

### Após instalação com setup.py:
Se você instalou usando `python setup.py install`, você pode executar:

```bash
anafis
```

### Executando a partir do código fonte:
Para iniciar o AnaFis a partir do diretório do código fonte, execute:

```bash
python run.py
```

A aplicação mostrará uma tela de carregamento e então abrirá a interface principal.

## Funcionalidades Principais

### Funcionalidade Central
- **Ajuste de Curvas**: Ajuste avançado de curvas com funções definidas pelo usuário e modelos integrados
- **Propagação de Incertezas**: Cálculo de propagação de incertezas para fórmulas arbitrárias usando matemática simbólica
- **Suporte Multi-idioma**: Interface disponível em Português e Inglês
- **Visualização em Tempo Real**: Gráficos interativos que atualizam em tempo real durante o ajuste

### Recursos da Interface
- **Interface com Abas**: Trabalhe com múltiplas análises simultaneamente
- **Troca de Idioma**: Mude o idioma da interface instantaneamente sem reiniciar
- **UI Moderna**: Interface limpa e intuitiva construída com tkinter
- **Capacidades de Exportação**: Exporte gráficos em vários formatos (PNG, PDF, SVG)

### Ferramentas Avançadas
- **Funções Personalizadas**: Defina e use modelos matemáticos personalizados para ajuste
- **Estimação de Parâmetros**: Estimação avançada de parâmetros com cálculo de incerteza
- **Importação de Dados**: Suporte para arquivos CSV e texto separado por tabulação
- **Gerenciamento de Histórico**: Mantenha registro de análises e resultados anteriores

## Formato do Arquivo de Dados

AnaFis suporta arquivos .csv ou .txt separados por tabulação com a seguinte estrutura de colunas:

```
x    σx    y    σy
```

**Exemplo de arquivo de dados:**
```
1.0  0.1   2.0  0.2
2.0  0.1   4.1  0.2
3.0  0.1   6.2  0.2
4.0  0.1   7.9  0.2
```

**Descrição das colunas:**
- `x`: Valores da variável independente
- `σx`: Incerteza (desvio padrão) em x
- `y`: Valores da variável dependente
- `σy`: Incerteza (desvio padrão) em y

## Guia de Uso

### Módulo de Ajuste de Curvas
1. **Carregar Dados**: Use o botão "Carregar Dados" para importar seu arquivo de dados
2. **Selecionar Modelo**: Escolha entre modelos predefinidos ou defina uma função personalizada
3. **Definir Parâmetros**: Forneça estimativas iniciais dos parâmetros
4. **Executar Ajuste**: Clique em "Ajustar" para executar o algoritmo de ajuste de curvas
5. **Analisar Resultados**: Visualize parâmetros do ajuste, incertezas e estatísticas de qualidade do ajuste
6. **Exportar**: Salve gráficos e resultados no formato de sua preferência

### Módulo Calculadora de Incertezas
1. **Definir Fórmula**: Insira sua expressão matemática usando notação simbólica
2. **Adicionar Variáveis**: Especifique variáveis com seus valores e incertezas
3. **Calcular**: A aplicação computará a propagação de incertezas usando derivadas parciais
4. **Ver Resultados**: Veja o resultado final com a incerteza calculada
5. **Visualização de Fórmulas**: Visualize fórmulas renderizadas em LaTeX para melhor compreensão

## Funções Matemáticas Suportadas

A aplicação suporta funções matemáticas padrão incluindo:
- Operações básicas: `+`, `-`, `*`, `/`, `**`
- Trigonométricas: `sin`, `cos`, `tan`, `asin`, `acos`, `atan`
- Logarítmicas: `log`, `ln`, `exp`
- Hiperbólicas: `sinh`, `cosh`, `tanh`
- Constantes: `pi`, `e`

## Suporte a Idiomas

AnaFis suporta interfaces em Português e Inglês. Você pode trocar idiomas usando o menu dropdown na barra de ferramentas principal. A mudança de idioma se aplica a todos os elementos da interface e atualiza todas as abas abertas imediatamente.

## Solução de Problemas

### Problemas Comuns
- **Ajuste não converge**: Tente valores iniciais diferentes para os parâmetros ou verifique a qualidade dos dados
- **Erros grandes no ajuste**: Revise os valores de incerteza e a adequação do modelo
- **tkinter ausente**: Instale via gerenciador de pacotes do SO ou certifique-se de que está incluído na instalação do Python
- **Erros de importação**: Verifique se todas as dependências estão instaladas com as versões corretas

### Dicas de Performance
- Para grandes conjuntos de dados, considere pré-processamento ou amostragem dos dados
- Funções personalizadas complexas podem requerer maior tempo de computação
- Salve seu trabalho frequentemente ao trabalhar com análises grandes

## Criando Executável

Para criar um executável autônomo para Windows:

### Pré-requisitos
```bash
pip install pyinstaller
```

### Processo de Compilação
1. Use os scripts de compilação fornecidos:
   ```cmd
   # Windows Batch
   build_exe.bat
   ```

2. Ou compile manualmente:
   ```bash
   python -m PyInstaller --clean AnaFis.spec
   ```

3. O executável será criado em `dist\AnaFis\AnaFis.exe`

### Configuração da Compilação
- O arquivo `AnaFis.spec` contém todas as configurações de compilação
- Inclui todas as dependências e arquivos de dados necessários
- Otimizado para tamanho e performance
- Cria uma distribuição portátil

Para mais detalhes, veja [DISTRIBUTION.md](DISTRIBUTION.md).

## Requisitos do Sistema

- **Sistema Operacional**: Windows, macOS ou Linux
- **Python**: Versão 3.8 ou mais recente
- **Memória**: Mínimo de 4GB RAM recomendado
- **Armazenamento**: Pelo menos 100MB de espaço livre para instalação

## Roadmap

### Próximas Funcionalidades
- **Integração Completa de Configurações**: Suporte completo a temas com modos claro/escuro/automático
- **Tabelas Estilo Excel**: Capacidades de entrada e edição de dados estilo planilha
- **Módulo de Resolução de Equações**: Solucionador simbólico e numérico de equações
- **Visualização Avançada de Dados**: Gráficos 3D, opções de personalização avançadas
- **Gerenciamento de Arquivos**: Arquivos de projeto, menu de arquivos recentes, funcionalidade de salvamento automático

Veja [TODO.md](TODO.md) para o roteiro completo de desenvolvimento e planejamento de funcionalidades.

## Contribuições

AnaFis está aberto para contribuições. Sinta-se à vontade para enviar issues, solicitações de recursos ou pull requests para melhorar a aplicação.

## Licença

Este projeto está disponível sob termos de licenciamento de código aberto. Veja o arquivo de licença para detalhes.
