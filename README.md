
  <h1 align="left"> Suicides Around The World</h1>
  <h5 align="left"> This is an exploratory analysis of suicides around the world using Microsoft excel</h3>

<p align="center">
  <img src= "https://user-images.githubusercontent.com/35836370/229316201-10b84d68-6dc8-4ae2-b876-163e63e19414.jpg" width="780"/>
</p>

<!-- <picture>
 <source media="(prefers-color-scheme: dark)" srcset="https://media.istockphoto.com/id/477120416/photo/suicide-word-cloud-with-abstract-background.jpg?s=612x612&w=0&k=20&c=9LsuqnCrjVSShk3Pmkn-U-K2FjI9tTHWyMXoiMLRLeo=" width="1000" height="300"/>
 <source media="(prefers-color-scheme: light)" srcset="https://media.istockphoto.com/id/477120416/photo/suicide-word-cloud-with-abstract-background.jpg?s=612x612&w=0&k=20&c=9LsuqnCrjVSShk3Pmkn-U-K2FjI9tTHWyMXoiMLRLeo=" width="1000" height="300"/>
 <img alt="An image with text of suicide and risk factors" src="https://media.istockphoto.com/id/477120416/photo/suicide-word-cloud-with-abstract-background.jpg?s=612x612&w=0&k=20&c=9LsuqnCrjVSShk3Pmkn-U-K2FjI9tTHWyMXoiMLRLeo=" width="1000" height="300"/>
</picture>
-->

<details>
  <summary>Introduction </summary>
      Suicide is death caused by injuring oneself with the intent to die. A suicide attempt is when someone harms themselves with any intent to end their       life,but they do not die as a result of their actions.<sup>1</sup>
      Suicide affects all ages. In 2020,in the United States suicide was among the top 9 leading causes of death for people ages 10-64. Suicide was the         second leading cause of death for people ages 10-14 and 25-34.<sup>2</sup>
      Suicide and suicide attempts cause serious emotional, physical, and economic impacts. People who attempt suicide and survive may experience serious       injuries that can have long-term effects on their health. They may also experience depression and other mental health concerns.<sup>3</sup>
      Suicide and suicide attempts affect the health and well-being of friends, loved ones, co-workers, and the community. When people die by suicide,         their surviving family and friends may experience shock, anger, guilt, symptoms of depression or anxiety, and may even experience thoughts of             suicide themselves.<sup>3</sup>
      The good news is that more than 90% of people who attempt suicide and survive never go on to die by suicide.<sup>4</sup>
</details>


<details>
  <summary>Problem Statements </summary>
  <ol>
      <li>Which Continent has highest prevalence of suicides</li>
      <li>Which Country has the highest prevalence of suicides</li>
      <li>Which year had the highest prevalence of suicides</li>
      <li>Is there a relationship between suicide rates and a country's GDP</li>
      <li>Is there a relationship between suicide rates and a country's human developmental index</li>
      <li>Is there a relationship between suicide rates and a country's human developmental index</li>
    
    </li>
  </ol>
</details>


<details>
  <summary>Datasets</summary>
  The datasets were gotten from:
  <ul>
    <li> <a href="https://www.healthdata.org/">Gapminder</a> : The data consists of number of suicides per country per year spanning from year 1990 to year 2019 ,there are 31 columns, 205 rows from 204                 countries, downloaded in xlsx format, when loaded into excel the data is in a wide format.   
    </li>
    <p><img src= "https://user-images.githubusercontent.com/35836370/229313129-88edf0d8-dd0a-44c8-aa57-91d20be2f80f.jpeg"/></p>
    <li> <a href="https://statisticstimes.com/geography/countries-by-continents.php">Countries by Continents</a> : in order to work with continents ,I merged the table from this site which had coubtries               and continents with the table from gapminder using the excel query editor.
    </li>
  </ul>
  </details>
  
  <details>
      <summary>Data Cleaning And Transformation Process</summary>
          <p>The data from gapminder was cleaned using the power query editor , which included:</p>
              <ul>
              <li>Changing the data type</li>
              <li>Remove the ending 'k'</li>
              <li>Remove duplicates</li>
              <li>Check for spelling Errors etc</li>
              </ul>
  </details>
  
      <p> process of converting my cleaned table from wide format to long format, press alt+d+p to ring up the PivotTable and PivotChart Wizard screen,Select “Multiple Consolidation ranges“ then Click “Next“.Select “I will create the page fields“ then Click “Next“.In Range input select the entire data range “'clean_data_ori (2)'!$A$1:$AE$205” then click “Next”,Select “New worksheet” and Click “Finish” </p>
  <p> to get the data for continent from the website , i clicked o data buton , get data from the web and pasted the link, press ok. it would open the power query editor</p>
</details>


<details>
    <summary>Reference</summary>
      <ol>
       <li>Crosby A, Ortega L, Melanson C. [Self-directed violence surveillance: Uniform definitions and recommended data elements, version 1.0 PDF – 1MB](https://www.cdc.gov/suicide/pdf/self-directed-violence-a.pdf)(2011) Atlanta, GA: Centers for Disease Control and Prevention, National Center        for Injury Prevention and Control.
       </li>
        <li>CDC.CDC WONDER: Underlying cause of death, 1999–2019. Atlanta, GA: US Department of Health and Human Services, CDC; 2020.[https://wonder.cdc.gov/Deaths-by-Underlying-Cause.html]
        </li>
        <li>Chapman A, Dixon-Gordon K. (2007) [Emotional antecedents and consequences of deliberate self-harm and suicide attempts]                               (https://onlinelibrary.wiley.com/doi/full/10.1521/suli.2007.37.5.543). Suicide & Life Threatening Behavior; 37(5): 543-552.</li>
        <li>Owens D, Horrocks J, House A. (2002) Fatal and non-fatal repetition of self-harm. Systematic review. Br J Psychiatry. Sep; 181:193-9.</li>
     </ol>
</details>
