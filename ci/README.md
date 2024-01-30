# Continuous Integration<br>
Conceitos<br>

**Problema - Poucos momentos de integração**<br>
Risco maior ao "commitar" muitas alterações de uma única vez.<br>
<kbd>
    <img src="https://github.com/fabiokerber/CI_CD/blob/main/img/030120221105.png">
</kbd>
<br />
<br />

**Integrações frequentes contínuas**<br>
Entregas frequentes e com menor criticidadade.<br>
<kbd>
    <img src="https://github.com/fabiokerber/CI_CD/blob/main/img/030120221107.png">
</kbd>
<br />
<br />

**Multi-Repo vs Mono-Repo**<br>
Mono-Repo - Único repositório, refatoração melhor, porém controle e organização mais complexa.<br>
<kbd>
    <img src="https://github.com/fabiokerber/CI_CD/blob/main/img/030120221111.png">
</kbd>
<br />
<br />

**Boas práticas**<br>
<kbd>
    <img src="https://github.com/fabiokerber/CI_CD/blob/main/img/030120221119.jpg">
</kbd>
<br />
<br />

**Comparando Branches**<br>
- *Temporários (branches locais)* - São branches localizados apenas na máquina local e deverão se extiguir, são utilizados para organizar fluxos de trabalho e depois realizar o commit.<br>
- *Feature Branches* - São utilizados para implementar funcionalidades ou orientar tarefas.<br>
- *Historical Branches (master e develop)* - As alterações ficam organizadas em commits baseados na cronologia no caso de um projeto de software.<br>
- *Environment Branches (Staging e Production)* - Existem branches que são baseados no ambiente, isto é, em que espaço é realizado o deploy.<br>
- *Maintenance Branches (Release e Hotfix)* - Temos, ainda, os branches de manutenção do sistema.<br>
- "Trunk-Based Development is a branching model that reduces this distance (between branches) to the minimum."<br>
<kbd>
    <img src="https://github.com/fabiokerber/CI_CD/blob/main/img/030120221135.jpg">
</kbd>
<br />
<br />

**Github Flow**<br>
<kbd>
    <img src="https://github.com/fabiokerber/CI_CD/blob/main/img/030120221157.JPG">
</kbd>
<br />
<br />

**Gitlab Flow**<br>
<kbd>
    <img src="https://github.com/fabiokerber/CI_CD/blob/main/img/030120221200.JPG">
</kbd>
<br />
<br />

**Feature Flag**<br>
*Feature Flag* - O código é inserido no master, mas ele não é visível para a equipe. O Feature flag serve também para testar funcionalidades, por exemplo.<br>
<kbd>
    <img src="https://github.com/fabiokerber/CI_CD/blob/main/img/030120221308.JPG">
</kbd>
<br />
<br />

**Merge vs Rebase**<br>
*Rebase* - "Merge" estado atual do Master para a branch que desejar. Develop atualizada com código da Master.<br>
<kbd>
    <img src="https://github.com/fabiokerber/CI_CD/blob/main/img/030120221319.JPG">
</kbd>
<br />
<br />

**TTD**<br>
*TDD (Test Drive Development)* - Os testes em integração contínua são sobre feedback do software, como a maioria dos métodos ágeis.<br>
<kbd>
    <img src="https://github.com/fabiokerber/CI_CD/blob/main/img/030120221329.JPG">
</kbd>
<br />
<br />

**Testes Automatizados**<br>
Existem diversas categorias e níveis de testes automatizados, aqui descaremos três: *unit tests*, *integration tests* e *functional tests*.<br>
- Os *unit tests* verificam unidades, como métodos e funções dentro do software. São os testes mais rápidos, baratos de escrever e sua manutenção é simples.<br>
- Os *testes de integração* são de um nível mais alto, e testam a relação de elementos, como por exemplo um banco de dados e o software. A realização destes testes é mais lenta, afinal possuem um outro grau de complexidade.<br>
- Testes de um nível ainda maior, são os *functional tests*, que testam o sistema completo e garante a correção de funcionalidades no ponto de vista do cliente.<br>
- Uma técnica comum é executar o que chamamos de *smoke tests*. Na prática, trata-se de uma seleção de testes que garantem que as funcionalidades mais importantes do sistema estejam operando corretamente. Esses testes avaliam um conjunto menor de elementos, por isso são mais rápidos, e dessa maneira teremos a garantia de que o software está operante em sua estrutura básica.<br>
Obs: Sempre importante coletar os *feedbacks* sobre cada teste.<br>
<kbd>
    <img src="https://github.com/fabiokerber/CI_CD/blob/main/img/030120221331.JPG">
</kbd>
<br />
<br />

**Build e Testes Automatizados**<br>
<kbd>
    <img src="https://github.com/fabiokerber/CI_CD/blob/main/img/030120221428.jpg">
</kbd>
<br />
<br />