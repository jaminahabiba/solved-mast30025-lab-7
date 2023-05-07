Download Link: https://assignmentchef.com/product/solved-mast30025-lab-7
<br>



<ol>

 <li>Recall the joint confidence region for the parameters of a full rank linear model:</li>

</ol>

(<strong>b </strong>− <em>β</em>)<em><sup>T</sup>X<sup>T</sup>X</em>(<strong>b </strong>− <em>β</em>) ≤ <em>ps</em><sup>2</sup><em>f<sub>α</sub>.</em>

Use this to derive a test for the hypothesis <em>H</em><sub>0 </sub>: <em>β </em>= <em>β</em><sup>∗</sup>. Show that this test is equivalent to the test for <em>H</em><sub>0 </sub>: <em>β </em>= <em>β</em><sup>∗ </sup>obtained using the general linear hypothesis.

<ol start="2">

 <li>Load the beef dataset from the website:</li>

</ol>

<em>&gt; beef &lt;- read.csv(</em><sup>’</sup><em>../data/beef.csv</em><sup>’</sup><em>)</em>

In the USA, the Cattlemen’s Beef Board and the National Cattlemen’s Beef Association promote the consumption of beef with an advertising campaign using the theme“Beef: it’s what’s for dinner”. The campaign is paid for by the “Beef Checkoff”, a law that requires all cattle producers to pay $1 per head of cattle sold to support beef/veal promotion and research. In 1988 the Missoulian newspaper surveyed the cattle growers of Montana, and for each of Montana’s 56 counties reported the percent of growers voting “yes” for the checkoff.

In this question we explain the size of the yes vote in terms of the characteristics of the farms in each county. Data on farms is taken from the U.S. Bureau of the Census, City and County Data Book, 1986. The variables given in the dataset are:

<strong>yes </strong>Percentage of farmers voting “yes” for the checkoff <strong>big </strong>Percentage of farms with 500 acres or more <strong>prin </strong>Percentage of operators whose principle income is farming <strong>size </strong>Average size of farm (hundreds of acres) <strong>val </strong>Average value of products sold ($1000’s) <strong>live </strong>Percentage of products sold from livestock and poultry <strong>sale </strong>Percentage of farms with sales of $100,000 or more

<ul>

 <li>Use pairs to plot the data. Is there any evidence of non-linearity or heteroskedasticity?</li>

 <li>Using the add1 and drop1 commands, use forward and backward selection to find parsimonious models for yes.</li>

 <li>Using the step command, starting from a model with just an intercept, use the AIC and stepwise selection to choose a model.</li>

 <li>Show that the model found in 2c can be improved by adding the interaction term size*sale. (Important here is how you judge “improved”.)</li>

</ul>

Use stepwise selection again to see if adding size*sale can let you remove any other variables from the model.

<ul>

 <li>Suppose that <em>β</em><sub>1</sub>, <em>β</em><sub>2 </sub>and <em>β</em><sub>12 </sub>are the coefficients of <em>x</em><sub>1 </sub>= size, <em>x</em><sub>2 </sub>= sale and size*sale, in the model from 2d. Plot <em>β</em><sub>1</sub><em>x</em><sub>1</sub>+<em>β</em><sub>2</sub><em>x</em><sub>2</sub>+<em>β</em><sub>12</sub><em>x</em><sub>1</sub>∗<em>x</em><sub>2 </sub>as a function of (<em>x</em><sub>1</sub><em>,x</em><sub>2</sub>), to see the combined effect of these variables on the yes vote. You may need the wireframe function from the lattice library, and also grid.</li>

 <li>Repeat the above question using the model with no size*sale interaction term from 2c.</li>

 <li>Use the diagnostic plots provided by R to assess the model from 2d.</li>

</ul>

Refer back to 2a; do you need to transform the data and start again?

<ul>

 <li>Which are the most important variables when it comes to predicting the yes vote? In deciding this, take into account the average size of the variables as well as the size of the fitted coefficients.</li>

</ul>

1

<ol start="3">

 <li>Load and examine the dataset trees using</li>

</ol>

<em>&gt; data(trees)</em>

<em>&gt; ?trees</em>

<em>&gt; pairs(trees)</em>

<table width="406">

 <tbody>

  <tr>

   <td width="126">


    <table width="121">

     <tbody>

      <tr>

       <td width="19"> </td>

       <td colspan="3" width="55"> </td>

       <td colspan="2" width="37">●●●●●●</td>

       <td width="10">●</td>

      </tr>

      <tr>

       <td width="19">●●●</td>

       <td colspan="3" width="55">●● ●●●●●●●●●● ●●●●●●●●</td>

       <td colspan="2" width="37">●</td>

       <td width="10"> </td>

      </tr>

      <tr>

       <td width="19"> </td>

       <td width="18"> </td>

       <td width="18"> </td>

       <td width="18"> </td>

       <td width="18"> </td>

       <td width="18"> </td>

       <td width="10"> </td>

      </tr>

      <tr>

       <td width="19"></td>

       <td width="18"></td>

       <td width="18"></td>

       <td width="18"></td>

       <td width="18"></td>

       <td width="18"></td>

       <td width="10"></td>

      </tr>

     </tbody>

    </table></td>

   <td width="265">


    <table width="254">

     <tbody>

      <tr>

       <td rowspan="7" width="45">●           ●●●●           ●        ●</td>

       <td rowspan="7" width="23">●●● ●●●●●●</td>

       <td rowspan="7" width="54">●●●●●●●●           ●●●●●●           ●</td>

       <td rowspan="7" width="13"> </td>

       <td rowspan="7" width="120">Volume</td>

       <td width="0"></td>

      </tr>

     </tbody>

    </table></td>

   <td width="15"></td>

  </tr>

 </tbody>

</table>

8 10 12 14 16 18 20                                                               10         30         50         70

We will model the volume of a black cherry tree as a function of its girth and height.

<ul>

 <li>By calculating <em>R</em>(<em>γ</em><sub>1</sub>|<em>γ</em><sub>2</sub>) and <em>SS<sub>Res </sub></em>from the data <strong>y </strong>and design matrix <em>X</em>, use an F test to determine if including the variable Height significantly improves the model fitted using only Girth (and an intercept).</li>

</ul>

Repeat the test using the lm and anova commands, to see if you get the same numbers.

<ul>

 <li>Add variables Girth squared and Girth squared times Height to the model, then use stepwise selection to simplify the model. (You can use step for this step.) Comment on the form of your final model.</li>

 <li>Use diagnostic plots to check the fit of your final model.</li>

</ul>

2