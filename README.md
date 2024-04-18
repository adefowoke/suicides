```html
  <h1 align="left"> Suicides Around The World</h1>
  <h5 align="left"> This is an exploratory analysis of suicides around the world using Microsoft Excel </h3>

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
      Suicide is death caused by injuring oneself with the intent to die. A suicide attempt is when someone harms themselves with any intent to end their       life, but they do not die as a result of their actions.<sup>1</sup>
      Suicide affects all ages. In 2020, in the United States, suicide was among the top 9 leading causes of death for people ages 10-64. Suicide was the         second leading cause of death for people ages 10-14 and 25-34.<sup>2</sup>
      Suicide and suicide attempts cause serious emotional, physical, and economic impacts. People who attempt suicide and survive may experience serious       injuries that can have long-term effects on their health. They may also experience depression and other mental health concerns.<sup>3</sup>
      Suicide and suicide attempts affect the health and well-being of friends, loved ones, co-workers, and the community. When people die by suicide,         their surviving family and friends may experience shock, anger, guilt, symptoms of depression or anxiety, and may even experience thoughts of suicide themselves.<sup>3</sup>
      The good news is that more than 90% of people who attempt suicide and survive never go on to die by suicide.<sup>4</sup>
</details>


<details>
  <summary>Problem Statements </summary>
  <ol>
      <li>Which Continent has the highest prevalence of suicides</li>
      <li>Which Country has the highest prevalence of suicides</li>
      <li>Which year had the highest prevalence of suicides</li>
      <li>Is there a relationship between suicide rates and a country's GDP</li>
      <li>Is there a relationship between suicide rates and a country's human developmental index</li>
      <li>Is there a relationship between suicide rates and a country's human developmental index</li>
    
  </ol>
</details>


<details>
  <summary>Collection of Datasets</summary>
  The datasets were gotten from:
  <ul>
    <li> <a href="https://www.healthdata.org/">Gapminder</a>: The data consists of the number of suicides per country per year spanning from the year 1990 to the 
            In 2019, there are 31 columns, and 205 rows from 204 countries, downloaded xlsx format when loaded into Excel the data is in a wide format.   
    </li>
    <p><img src= "https://user-images.githubusercontent.com/35836370/229313129-88edf0d8-dd0a-44c8-aa57-91d20be2f80f.jpeg"/></p>
    <li> <a href="https://statisticstimes.com/geography/countries-by-continents.php">Countries by Continents</a>: to work with continents, I downloaded data from 
         this site, which includes countries and their corresponding continent, this was done using the power query editor.
         <p>Open Excel, open a new Excel worksheet, from the ribbon, select data, and select from the web. This opens a From web pop-up, insert the URL, leave the 
              default basic, and press ok. It opens another pop-up Access Web Content, from the drop-down option, choose the one that ends with ".php", and press 
              connect. 
             This opens the Navigator window, select "Countries or Areas". select Transform. This takes you to the power Query Editor. I want to use only the 
             column with country and continent. Drag the continent close to the country for easy selection, select "country", and "continent" while holding down 
             the shift key in Windows, right-click, from the options provided, and select Remove other columns. An overview of the data shows no missing data. 
             click "close and apply". This file can be saved on the local machine to be used whenever needed.
        </p>
    </li>
    <p align="middle"><img src="/pic1.jpeg" width="48%" /></p>
  </ul>
  </details>
  
  <details>
      <summary>Data Cleaning And Transformation Process</summary>
          <p>The data from gapminder (suicide data) was cleaned using the Excel power query editor, which included:</p>
              <ul>
                  <li>Always make a copy of your data before making any changes to it, this acts as a fallback when you need the original data</li>
                  <li>Freeze top row: Select the View tab, select Freeze panes, and select Freeze top row
                  </li>
                  <li>Find and replace 'k':  An overview of the data shows there are some rows with 'K' to them since there is no avenue to confirm why there is 
                      'k' in the data, I will assume those 
                      figures are in thousands. Selecting Find & select in the home tab, brings a pop-up, enter 'k', and press findall. it shows that there are 
                      343 cells affected by this, so manually fixing 
                      this would be a waste of time and a high risk of making a mistake is there.
                      Select the whole sheet, you can select A1, hold down 'shift + Ctrl', press the 'end' key, and press the 'pgDn' key. Select Sort&Filter, this 
                      adds a filter icon to the first roll.
                      Click on the filter icon on 1990, select Number Filters, Custom Filter, this brings out the Custom Autofilter pop-up, select the drop-down 
                      and choose 'ends with', enter 'k' in the adjacent 
                      box, and press ok. this shows only 204 of the 343 cells. This is because I filtered using the 1990 column, meaning there are still cells 
                      with the 'k' value not displayed. I was unable to 
                      get a method that could do it at once across all the years.
                      This is the formula to remove the 'k' and multiply the cell with 'k' by 1000: =IF(RIGHT(B63,1)="k", LEFT(B63, FIND("k", B63)-1)*1000, B63)
                  </li>
                  <li>Remove duplicates</li>
                  <li>Check for spelling errors etc</li>
                  <li>Merge the 2 tables using vlookup function: =VLOOKUP(A2,'Countries_Continent (2)'!A2:B250,2,FALSE) . Before using this formula,
                    <ul>
                       <li> Sort your tables A-Z</li>
                       <li> Ensure the table with the continent has been reformatted as a range and not a table, select the whole table, go to the table design 
                            tab, and click on "convert to range"</li>
                       <li> If the formula is not showing a value, check and make sure the cell is formatted as general and not text</li>
                       </ul>  
                  <li>Convert the table from a wide to a long format: The conversion is done to make creating a pivot table easier, which allows analysis much 
                      faster and easier as you can select the features you want to analyze. This involves using the power query editor:
                    <ul>
                      <li>Select the whole data range, click on the Data tab, and select from table or range</li>
                      <li>This fires up the power query editor, select the year columns, click on the transform tab</li>
                      <li>Select unpivot, this puts all the years in a single column , all the values in a single column</li>
                      <li>Name your columns appropriately</li>
                      <li>Click close and apply</li>
                    </ul>
                  </li>
                      <p align="center">
                          <img src="./Wide_table_format.png", width="55%", height="480", title="wide format"/>
                          <!--<img src="./77c88a49-b96b-46f0-aaee-49ea091d8951.jpg", width="55%", height="480", title="wide format"/>-->
                      &nbsp; &nbsp; &nbsp; &nbsp;
                          <img src="./Long_table_format.png", width="20%", height="240",title="long format"/> 
                     </p>
                    <!-- <p align="center"><img src="./799b660c-88ea-436c-8d41-d343f61a7861.jpg",width="48%", title="combined"/></p> -->
             </ul>
    </p>
</details>
<details>
      <summary>Summary Statistics And Visualizations</summary>
  Summary_table.png
</details>

<details>
  <summary>Challenges</summary>
    <ul>
      <li>Some countries were not added to the suicide data from the source</li>
      <li> Some countries were named differently in both tables, so it came up as N/A, I had to manually cross-check those countries</li>
      <li>I had to manually add Asia for Taiwan as there was no data for it</li>
      <li>No avenue to verify some of the discrepancies found in the dataset</li>
      
   </ul>
</details>


<details>
    <summary>Reference</summary>
      <ol>
       <li>Crosby A, Ortega L, Melanson C. [Self-directed violence surveillance: Uniform definitions and recommended data elements, version 1.0 PDF – 1MB](https://www.cdc.gov/suicide/pdf/self-directed-violence- 
           a.pdf)(2011) Atlanta, GA: Centers for Disease Control and Prevention, National Center        for Injury Prevention and Control.
       </li>
       <li>CDC.CDC WONDER: Underlying cause of death, 1999–2019. Atlanta, GA: US Department of Health and Human Services, CDC; 2020.[https://wonder.cdc.gov/Deaths-by-Underlying-Cause.html]
       </li>
       <li>Chapman A, Dixon-Gordon K. (2007) [Emotional antecedents and consequences of deliberate self-harm and suicide attempts]                               
           (https://onlinelibrary.wiley.com/doi/full/10.1521/suli.2007.37.5.543). Suicide & Life-Threatening Behavior; 37(5): 543-552.
       </li>
       <li>Owens D, Horrocks J, House A. (2002) Fatal and non-fatal repetition of self-harm. Systematic review. Br J Psychiatry. Sep; 181:193-9.</li>
     </ol>
</details>
```html
