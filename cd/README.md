# Continuous Delivery<br>
Conceitos<br>

**Pipeline de Deploy**<br>
<kbd>
    <img src="https://github.com/fabiokerber/CI_CD/blob/main/img/100120220920.JPG">
</kbd>
<br />
<br />

**Colaboração**<br>
Todos colaborando com o mesmo objetivo!<br>
<kbd>
    <img src="https://github.com/fabiokerber/CI_CD/blob/main/img/100120220925.JPG">
</kbd>
<br />
<br />

**Etapas de Deploy**<br>
**Release Antipatterns = Bad trip!!**<br>
&nbsp;&nbsp;&nbsp;&nbsp;Gerenciamento manual de ambientes > Sempre garantir que os testes sejam realizados nos ambientes de forma correta (Homologação deve estar igual à Produção, garantindo assim que funcionará corretamente em Produção).<br>
&nbsp;&nbsp;&nbsp;&nbsp;- **Resultado:** Deploy não confiável.<br>
&nbsp;&nbsp;&nbsp;&nbsp;- **Regra:** Todos os ambientes são tratados como código, versionado e criados de maneira *automatizada*.<br>
</br>
&nbsp;&nbsp;&nbsp;&nbsp;Dev nunca viu Ops?<br>
&nbsp;&nbsp;&nbsp;&nbsp;Deploys longos? Horas ou dias?<br>
&nbsp;&nbsp;&nbsp;&nbsp;Rollbacks frequentes?<br>
&nbsp;&nbsp;&nbsp;&nbsp;-  **Resultado:** Deploy lento, propício ao erro, não confiável.<br>
&nbsp;&nbsp;&nbsp;&nbsp;-  **Regra:** Somente duas tarefas devem ser executadas manualmente:<br> 
&nbsp;&nbsp;&nbsp;&nbsp;1) Escolher a Release.<br> 
&nbsp;&nbsp;&nbsp;&nbsp;2) Qualquer um pode clicar no "Deploy Button", pois todo o deploy está "codado" e automatizado.<br>
</br>
&nbsp;&nbsp;&nbsp;&nbsp;Deploy apenas no *fim do ciclo* de desenvolvimento(não é certeza de que o deploy será realizado com sucesso em produção).<br>
&nbsp;&nbsp;&nbsp;&nbsp;- **Resultado:** Pouca colaboração, problemas só aparecem no dia da publicação, não confiável e nem rápido, *"achismo"*.<br>
&nbsp;&nbsp;&nbsp;&nbsp;- **Regra:** Deploy faz parte do desenvolvimento desde a primeira interação, todos definem um *delivery team*.<br>
<kbd>
    <img src="https://github.com/fabiokerber/CI_CD/blob/main/img/100120220928.JPG">
</kbd>
<br />
<br />

**Entrega Contínua vs Deploy Contínuo**<br>
<kbd>
    <img src="https://github.com/fabiokerber/CI_CD/blob/main/img/100120221002.JPG">
</kbd>
<br />
<br />

**Antes de começar com CD**<br>
Master com Build OK podendo ser deployado a qualquer momento.<br>
Testes sempre sendo realizados.<br>
Ambientes sempre deployáveis em qualquer ambiente e em código!.<br>
<kbd>
    <img src="https://github.com/fabiokerber/CI_CD/blob/main/img/100120221041.JPG">
</kbd>
<br />
<br />

**Princípios da Entrega Contínua**<br>
Entrega contínua deve ser realizada a qualquer momento, senão não há este conceito.<br>
"Entregar software com alta qualidade e grande valor de maneira eficiente, rápido e confiável".<br>
Ambientes sempre *"deployáveis"* em qualquer ambiente e em código!.<br>
&nbsp;&nbsp;&nbsp;&nbsp;I. Automatize
&nbsp;&nbsp;&nbsp;&nbsp;II. Versione
&nbsp;&nbsp;&nbsp;&nbsp;III. Repita
&nbsp;&nbsp;&nbsp;&nbsp;IV. Garanta qualidade
&nbsp;&nbsp;&nbsp;&nbsp;V. Defina "done" < O que é pronto? 
&nbsp;&nbsp;&nbsp;&nbsp;VI. Crie *delivery team*
&nbsp;&nbsp;&nbsp;&nbsp;VII. Melhoria contínua
<br />
<br />

**Elementos da Entrega Contínua**<br>
Cultura DevOps<br>
&nbsp;&nbsp;&nbsp;&nbsp;- feedback, colaboração, confiança
&nbsp;&nbsp;&nbsp;&nbsp;- melhoria e aprendizagem contínua
Patterns<br>
&nbsp;&nbsp;&nbsp;&nbsp;- deployment pipeline
&nbsp;&nbsp;&nbsp;&nbsp;- deploy patterns (blue/green, canary, feature toogle)
Arquitetura<br>
&nbsp;&nbsp;&nbsp;&nbsp;- novas Propriedades: testability & deployability
&nbsp;&nbsp;&nbsp;&nbsp;- SOLID, Services, 12 Factor App
<br />
<br />

**Etapas / Stages do Pipeline de Deploy**<br>
Todas as etapas devem ser realizadas com sucesso.<br>
AAT = Automated Acceptance Tests<br>
UAT = User Acceptance Testing<br>
<kbd>
    <img src="https://github.com/fabiokerber/CI_CD/blob/main/img/100120221729.png">
</kbd>
<br />
<br />

**Boas práticas**<br>
- pipeline é a **única forma de deploy**<br>
- **mantém** o pipeline o mais **rápido** possível<br>
- **build** apenas uma **vez**<br>
- **build independente** do ambiente
- ambientes **iguais/semelhantes** (prd e hml)
- deploy sempre igual para **todos os ambientes**
<kbd>
    Build Unit Test > AAT > UAT > HML > PRD
</kbd>
<br />
<br />

**Boas práticas - Commit Stage (Continuous Integration)**<br>
<kbd>
    <img src="https://github.com/fabiokerber/CI_CD/blob/main/img/120120221609.jpg">
</kbd>
<br />
<br />

**Boas práticas - AAT (Automated Acceptance Tests)**<br>
Garantir que a aplicação como um todo, funcione!<br>
Testes demorados, caros.<br>
Testes de requisitos de negócio.<br>
<kbd>
    <img src="https://github.com/fabiokerber/CI_CD/blob/main/img/010220221020.jpg">
</kbd>
<br />
<br />

**UAT (User Acceptance Tests)**<br>
Usuário/Cliente que fará os testes neste stage.<br>
Feedback direto do cliente, já testando com as regras de negócio.<br>
"Our highest priority is to satisfy the **customer** through early and of *continuous delivery* **valuable software**.<br>
<kbd>
    <img src="https://github.com/fabiokerber/CI_CD/blob/main/img/010220221035.jpg">
</kbd>
<br />
<br />

**Capacity Testing Stage (User Acceptance Tests)**<br>
Reproduzir os cenários reais no ambiente de teste e validar se aguenta carga de utilização.<br>
<kbd>
    <img src="https://github.com/fabiokerber/CI_CD/blob/main/img/010220221041.jpg">
</kbd>
<kbd>
    <img src="https://github.com/fabiokerber/CI_CD/blob/main/img/010220221044.jpg">
</kbd>
<br />
<br />

**Releases de baixo risco**<br>
<kbd>
    <img src="https://github.com/fabiokerber/CI_CD/blob/main/img/010220221049.jpg">
</kbd>
<br />
<br />

**Deploy vs Release**<br>
Deploy - Versão "lançada".<br>
Release - Versão disponibilizada ao cliente.<br>
<kbd>
    <img src="https://github.com/fabiokerber/CI_CD/blob/main/img/010220221053.jpg">
</kbd>
<br />
<br />

**Deploy vs Release (Tipos de Release)**<br>
Técnicas de Release.<br>
<kbd>
    <img src="https://github.com/fabiokerber/CI_CD/blob/main/img/010220221054.jpg">
</kbd>
<kbd>
    <img src="https://github.com/fabiokerber/CI_CD/blob/main/img/010220221056.jpg">
</kbd>
<br />
<br />

**Blue-Green Deployment**<br>
Blue - Release atual.<br>
Green - Novo Release.<br>
Os ambientes ficam no ar caso seja necessário retornar a utilização do release anterior.<br>
Evita downtime.<br>
Rollback rápido.<br>
<kbd>
    <img src="https://github.com/fabiokerber/CI_CD/blob/main/img/010220221057.jpg">
</kbd>
<kbd>
    <img src="https://github.com/fabiokerber/CI_CD/blob/main/img/010220221059.jpg">
</kbd>
<br />
<br />

**Canary Release / Dark Launching**<br>
As duas versões são utilizadas ao mesmo tempo.<br>
Alguns usuários testers usam o Green e os demais continuam utilizando o Blue.<br>
É possível definir essa "Divisão", conforme melhor para o negócio.<br>
<kbd>
    <img src="https://github.com/fabiokerber/CI_CD/blob/main/img/010220221102.jpg">
</kbd>
<br />
<br />