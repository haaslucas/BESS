```python
import pandas as pd
import numpy as np
```


```python
M_energy_management_systems_2020_2022 = pd.read_csv('M_energy_management_systems_2020_2022.csv')
MJ_pv_iot = pd.read_csv('MJ_pv_iot.csv')
MJ_photovoltaic_iot = pd.read_csv('MJ_photovoltaic_iot.csv')
MJ_pv_scada = pd.read_csv('MJ_pv_scada.csv')
MJ_photovoltaic_scada = pd.read_csv('MJ_photovoltaic_scada.csv')
MJ_battery_energy_storage_system_scada = pd.read_csv('MJ_battery_energy_storage_system_scada.csv')
MJ_battery_energy_storage_system_data = pd.read_csv('MJ_battery_energy_storage_system_data.csv')
MJ_battery_energy_storage_system_iot = pd.read_csv('MJ_battery_energy_storage_system_iot.csv')
MJ_battery_energy_storage_system_control = pd.read_csv('MJ_battery_energy_storage_system_control.csv')
MJ_BESS_control = pd.read_csv('MJ_BESS_control.csv')
MJ_BESS_monitoring = pd.read_csv('MJ_BESS_monitoring.csv')
MJ_BESS_management = pd.read_csv('MJ_BESS_management.csv')
MJ_BESS_optimization = pd.read_csv('MJ_BESS_optimization.csv')
MJ_battery_energy_storage_system_monitoring = pd.read_csv('MJ_battery_energy_storage_system_monitoring.csv')
MJ_battery_energy_storage_system_optimization = pd.read_csv('MJ_battery_energy_storage_system_optimization.csv')
MJ_battery_energy_storage_system_management = pd.read_csv('MJ_battery_energy_storage_system_management.csv')

MJ = pd.concat([M_energy_management_systems_2020_2022, MJ_pv_iot, MJ_photovoltaic_iot, MJ_pv_scada, MJ_photovoltaic_scada,  MJ_battery_energy_storage_system_scada, MJ_battery_energy_storage_system_data, MJ_battery_energy_storage_system_iot, MJ_battery_energy_storage_system_control, MJ_BESS_control, MJ_BESS_monitoring, MJ_BESS_management, MJ_BESS_optimization, MJ_battery_energy_storage_system_monitoring, MJ_battery_energy_storage_system_optimization, MJ_battery_energy_storage_system_management  ] )


```


```python
len(MJ)
```




    4374




```python
MJ.nunique()

```




    Document Title                 2151
    Authors                        2076
    Author Affiliations            2023
    Publication Title               121
    Date Added To Xplore            739
    Publication Year                  7
    Volume                           67
    Issue                            15
    Start Page                     1791
    End Page                       1812
    Abstract                       2151
    ISSN                            121
    ISBNs                             0
    DOI                            2149
    Funding Information            1379
    PDF Link                       2151
    Author Keywords                1927
    IEEE Terms                     2141
    INSPEC Controlled Terms        1925
    INSPEC Non-Controlled Terms    1927
    Mesh_Terms                        2
    Article Citation Count          134
    Patent Citation Count             1
    Reference Count                 127
    License                           7
    Online Date                    1056
    Issue Date                        0
    Meeting Date                      0
    Publisher                         9
    Document Identifier              10
    dtype: int64




```python
MJ = MJ.drop_duplicates()
```


```python
len(MJ)
```




    2151




```python
if MJ['Article Citation Count']


MJ = MJ.sort_values(by = ['Article Citation Count'], ascending = [False])
```


```python
MJ.to_excel('MJ.xlsx')
```


```python
len(MJ)
```




    2151




```python
type(df)
```




    pandas.core.frame.DataFrame




```python
df.columns
```




    Index(['Document Title', 'Authors', 'Author Affiliations', 'Publication Title',
           'Date Added To Xplore', 'Publication Year', 'Volume', 'Issue',
           'Start Page', 'End Page', 'Abstract', 'ISSN', 'ISBNs', 'DOI',
           'Funding Information', 'PDF Link', 'Author Keywords', 'IEEE Terms',
           'INSPEC Controlled Terms', 'INSPEC Non-Controlled Terms', 'Mesh_Terms',
           'Article Citation Count', 'Patent Citation Count', 'Reference Count',
           'License', 'Online Date', 'Issue Date', 'Meeting Date', 'Publisher',
           'Document Identifier'],
          dtype='object')




```python
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Document Title</th>
      <th>Authors</th>
      <th>Author Affiliations</th>
      <th>Publication Title</th>
      <th>Date Added To Xplore</th>
      <th>Publication Year</th>
      <th>Volume</th>
      <th>Issue</th>
      <th>Start Page</th>
      <th>End Page</th>
      <th>...</th>
      <th>Mesh_Terms</th>
      <th>Article Citation Count</th>
      <th>Patent Citation Count</th>
      <th>Reference Count</th>
      <th>License</th>
      <th>Online Date</th>
      <th>Issue Date</th>
      <th>Meeting Date</th>
      <th>Publisher</th>
      <th>Document Identifier</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Energy Management and Optimization Methods for...</td>
      <td>R. H. Byrne; T. A. Nguyen; D. A. Copp; B. R. C...</td>
      <td>Sandia National Laboratories, Albuquerque, NM,...</td>
      <td>IEEE Access</td>
      <td>27 Mar 2018</td>
      <td>2018</td>
      <td>6</td>
      <td>NaN</td>
      <td>13231</td>
      <td>13260</td>
      <td>...</td>
      <td>NaN</td>
      <td>144.0</td>
      <td>NaN</td>
      <td>227.0</td>
      <td>OAPA</td>
      <td>24 Aug 2017</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Profit-Maximizing Planning and Control of Batt...</td>
      <td>Y. J. A. Zhang; C. Zhao; W. Tang; S. H. Low</td>
      <td>Department of Information Engineering, Chinese...</td>
      <td>IEEE Transactions on Smart Grid</td>
      <td>16 Feb 2018</td>
      <td>2018</td>
      <td>9</td>
      <td>2.0</td>
      <td>712</td>
      <td>723</td>
      <td>...</td>
      <td>NaN</td>
      <td>105.0</td>
      <td>NaN</td>
      <td>19.0</td>
      <td>IEEE</td>
      <td>4 May 2016</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Stochastic Optimal Planning of Battery Energy ...</td>
      <td>H. Alharbi; K. Bhattacharya</td>
      <td>Department of Electrical and Computer Engineer...</td>
      <td>IEEE Transactions on Sustainable Energy</td>
      <td>14 Dec 2017</td>
      <td>2018</td>
      <td>9</td>
      <td>1.0</td>
      <td>211</td>
      <td>227</td>
      <td>...</td>
      <td>NaN</td>
      <td>104.0</td>
      <td>NaN</td>
      <td>48.0</td>
      <td>IEEE</td>
      <td>11 Jul 2017</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Stochastic Multistage Coplanning of Transmissi...</td>
      <td>T. Qiu; B. Xu; Y. Wang; Y. Dvorkin; D. S. Kirs...</td>
      <td>Department of Electrical Engineering, Universi...</td>
      <td>IEEE Transactions on Power Systems</td>
      <td>20 Dec 2016</td>
      <td>2017</td>
      <td>32</td>
      <td>1.0</td>
      <td>643</td>
      <td>651</td>
      <td>...</td>
      <td>NaN</td>
      <td>100.0</td>
      <td>NaN</td>
      <td>33.0</td>
      <td>IEEE</td>
      <td>20 Apr 2016</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Load Frequency Control in Microgrids Based on ...</td>
      <td>M. Khooban; T. Niknam; M. Shasadeghi; T. Dragi...</td>
      <td>Department of Electrical and Electronic Engine...</td>
      <td>IEEE Transactions on Sustainable Energy</td>
      <td>20 Mar 2018</td>
      <td>2018</td>
      <td>9</td>
      <td>2.0</td>
      <td>853</td>
      <td>861</td>
      <td>...</td>
      <td>NaN</td>
      <td>92.0</td>
      <td>NaN</td>
      <td>36.0</td>
      <td>IEEE</td>
      <td>16 Oct 2017</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 30 columns</p>
</div>




```python
df.describe()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Publication Year</th>
      <th>Issue</th>
      <th>Start Page</th>
      <th>End Page</th>
      <th>Mesh_Terms</th>
      <th>Article Citation Count</th>
      <th>Patent Citation Count</th>
      <th>Reference Count</th>
      <th>Issue Date</th>
      <th>Meeting Date</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>505.000000</td>
      <td>95.000000</td>
      <td>505.000000</td>
      <td>505.000000</td>
      <td>0.0</td>
      <td>283.000000</td>
      <td>0.0</td>
      <td>473.000000</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>2019.481188</td>
      <td>17.515789</td>
      <td>9111.524752</td>
      <td>9117.958416</td>
      <td>NaN</td>
      <td>9.183746</td>
      <td>NaN</td>
      <td>23.543340</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>std</th>
      <td>1.300238</td>
      <td>34.096504</td>
      <td>33981.763326</td>
      <td>33983.453587</td>
      <td>NaN</td>
      <td>17.441335</td>
      <td>NaN</td>
      <td>16.287106</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>min</th>
      <td>2017.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>NaN</td>
      <td>1.000000</td>
      <td>NaN</td>
      <td>0.000000</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>2019.000000</td>
      <td>2.000000</td>
      <td>1.000000</td>
      <td>6.000000</td>
      <td>NaN</td>
      <td>1.000000</td>
      <td>NaN</td>
      <td>15.000000</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>2020.000000</td>
      <td>4.000000</td>
      <td>102.000000</td>
      <td>110.000000</td>
      <td>NaN</td>
      <td>3.000000</td>
      <td>NaN</td>
      <td>20.000000</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>2021.000000</td>
      <td>6.000000</td>
      <td>1341.000000</td>
      <td>1346.000000</td>
      <td>NaN</td>
      <td>8.000000</td>
      <td>NaN</td>
      <td>28.000000</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>max</th>
      <td>2022.000000</td>
      <td>99.000000</td>
      <td>214577.000000</td>
      <td>214585.000000</td>
      <td>NaN</td>
      <td>144.000000</td>
      <td>NaN</td>
      <td>227.000000</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
df[df['Article Citation Count']>10]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Document Title</th>
      <th>Authors</th>
      <th>Author Affiliations</th>
      <th>Publication Title</th>
      <th>Date Added To Xplore</th>
      <th>Publication Year</th>
      <th>Volume</th>
      <th>Issue</th>
      <th>Start Page</th>
      <th>End Page</th>
      <th>...</th>
      <th>Mesh_Terms</th>
      <th>Article Citation Count</th>
      <th>Patent Citation Count</th>
      <th>Reference Count</th>
      <th>License</th>
      <th>Online Date</th>
      <th>Issue Date</th>
      <th>Meeting Date</th>
      <th>Publisher</th>
      <th>Document Identifier</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Energy Management and Optimization Methods for...</td>
      <td>R. H. Byrne; T. A. Nguyen; D. A. Copp; B. R. C...</td>
      <td>Sandia National Laboratories, Albuquerque, NM,...</td>
      <td>IEEE Access</td>
      <td>27 Mar 2018</td>
      <td>2018</td>
      <td>6</td>
      <td>NaN</td>
      <td>13231</td>
      <td>13260</td>
      <td>...</td>
      <td>NaN</td>
      <td>144.0</td>
      <td>NaN</td>
      <td>227.0</td>
      <td>OAPA</td>
      <td>24 Aug 2017</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Profit-Maximizing Planning and Control of Batt...</td>
      <td>Y. J. A. Zhang; C. Zhao; W. Tang; S. H. Low</td>
      <td>Department of Information Engineering, Chinese...</td>
      <td>IEEE Transactions on Smart Grid</td>
      <td>16 Feb 2018</td>
      <td>2018</td>
      <td>9</td>
      <td>2.0</td>
      <td>712</td>
      <td>723</td>
      <td>...</td>
      <td>NaN</td>
      <td>105.0</td>
      <td>NaN</td>
      <td>19.0</td>
      <td>IEEE</td>
      <td>4 May 2016</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Stochastic Optimal Planning of Battery Energy ...</td>
      <td>H. Alharbi; K. Bhattacharya</td>
      <td>Department of Electrical and Computer Engineer...</td>
      <td>IEEE Transactions on Sustainable Energy</td>
      <td>14 Dec 2017</td>
      <td>2018</td>
      <td>9</td>
      <td>1.0</td>
      <td>211</td>
      <td>227</td>
      <td>...</td>
      <td>NaN</td>
      <td>104.0</td>
      <td>NaN</td>
      <td>48.0</td>
      <td>IEEE</td>
      <td>11 Jul 2017</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Stochastic Multistage Coplanning of Transmissi...</td>
      <td>T. Qiu; B. Xu; Y. Wang; Y. Dvorkin; D. S. Kirs...</td>
      <td>Department of Electrical Engineering, Universi...</td>
      <td>IEEE Transactions on Power Systems</td>
      <td>20 Dec 2016</td>
      <td>2017</td>
      <td>32</td>
      <td>1.0</td>
      <td>643</td>
      <td>651</td>
      <td>...</td>
      <td>NaN</td>
      <td>100.0</td>
      <td>NaN</td>
      <td>33.0</td>
      <td>IEEE</td>
      <td>20 Apr 2016</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Load Frequency Control in Microgrids Based on ...</td>
      <td>M. Khooban; T. Niknam; M. Shasadeghi; T. Dragi...</td>
      <td>Department of Electrical and Electronic Engine...</td>
      <td>IEEE Transactions on Sustainable Energy</td>
      <td>20 Mar 2018</td>
      <td>2018</td>
      <td>9</td>
      <td>2.0</td>
      <td>853</td>
      <td>861</td>
      <td>...</td>
      <td>NaN</td>
      <td>92.0</td>
      <td>NaN</td>
      <td>36.0</td>
      <td>IEEE</td>
      <td>16 Oct 2017</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Optimal Charging Control of Energy Storage and...</td>
      <td>C. Lin; D. Deng; C. Kuo; Y. Liang</td>
      <td>Department of Industrial Engineering and Manag...</td>
      <td>IEEE Transactions on Industrial Informatics</td>
      <td>4 Jun 2018</td>
      <td>2018</td>
      <td>14</td>
      <td>6.0</td>
      <td>2570</td>
      <td>2578</td>
      <td>...</td>
      <td>NaN</td>
      <td>66.0</td>
      <td>NaN</td>
      <td>28.0</td>
      <td>IEEE</td>
      <td>13 Dec 2017</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Battery ESS Planning for Wind Smoothing via Va...</td>
      <td>F. Zhang; K. Meng; Z. Xu; Z. Dong; L. Zhang; C...</td>
      <td>Key Laboratory of Power System Intelligent Dis...</td>
      <td>IEEE Transactions on Sustainable Energy</td>
      <td>20 May 2017</td>
      <td>2017</td>
      <td>8</td>
      <td>2.0</td>
      <td>695</td>
      <td>707</td>
      <td>...</td>
      <td>NaN</td>
      <td>55.0</td>
      <td>NaN</td>
      <td>35.0</td>
      <td>IEEE</td>
      <td>6 Oct 2016</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Cooperative Optimal Control of Battery Energy ...</td>
      <td>T. Zhao; Z. Ding</td>
      <td>School of Electrical and Electronic Engineerin...</td>
      <td>IEEE Transactions on Power Systems</td>
      <td>16 Feb 2018</td>
      <td>2018</td>
      <td>33</td>
      <td>2.0</td>
      <td>2292</td>
      <td>2300</td>
      <td>...</td>
      <td>NaN</td>
      <td>54.0</td>
      <td>NaN</td>
      <td>34.0</td>
      <td>IEEE</td>
      <td>18 Aug 2017</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Optimized Energy Management System to Reduce F...</td>
      <td>N. Anglani; G. Oriti; M. Colombini</td>
      <td>University of Pavia, Pavia, Italy; Naval Postg...</td>
      <td>IEEE Transactions on Industry Applications</td>
      <td>20 Nov 2017</td>
      <td>2017</td>
      <td>53</td>
      <td>6.0</td>
      <td>5777</td>
      <td>5785</td>
      <td>...</td>
      <td>NaN</td>
      <td>51.0</td>
      <td>NaN</td>
      <td>31.0</td>
      <td>IEEE</td>
      <td>31 Jul 2017</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Energy Storage Planning for Enhanced Resilienc...</td>
      <td>M. Nazemi; M. Moeini-Aghtaie; M. Fotuhi-Firuza...</td>
      <td>Department of Electrical and Computer Engineer...</td>
      <td>IEEE Transactions on Sustainable Energy</td>
      <td>20 Mar 2020</td>
      <td>2020</td>
      <td>11</td>
      <td>2.0</td>
      <td>795</td>
      <td>806</td>
      <td>...</td>
      <td>NaN</td>
      <td>50.0</td>
      <td>NaN</td>
      <td>67.0</td>
      <td>IEEE</td>
      <td>26 Mar 2019</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Optimizing LiFePO4 Battery Energy Storage Syst...</td>
      <td>B. Lian; A. Sims; D. Yu; C. Wang; R. W. Dunn</td>
      <td>Department of Electronic and Electrical Engine...</td>
      <td>IEEE Transactions on Sustainable Energy</td>
      <td>14 Dec 2016</td>
      <td>2017</td>
      <td>8</td>
      <td>1.0</td>
      <td>385</td>
      <td>394</td>
      <td>...</td>
      <td>NaN</td>
      <td>49.0</td>
      <td>NaN</td>
      <td>23.0</td>
      <td>IEEE</td>
      <td>15 Aug 2016</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Control of Battery Storage Systems for the Sim...</td>
      <td>E. Namor; F. Sossan; R. Cherkaoui; M. Paolone</td>
      <td>Distributed Electrical Systems Laboratory, Éco...</td>
      <td>IEEE Transactions on Smart Grid</td>
      <td>22 Apr 2019</td>
      <td>2019</td>
      <td>10</td>
      <td>3.0</td>
      <td>2799</td>
      <td>2808</td>
      <td>...</td>
      <td>NaN</td>
      <td>47.0</td>
      <td>NaN</td>
      <td>33.0</td>
      <td>OAPA</td>
      <td>28 Feb 2018</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>12</th>
      <td>An Improved Optimal Sizing Methodology for Fut...</td>
      <td>U. Akram; M. Khalid; S. Shafiq</td>
      <td>Electrical Engineering Department, King Fahd U...</td>
      <td>IEEE Access</td>
      <td>2 Mar 2018</td>
      <td>2018</td>
      <td>6</td>
      <td>NaN</td>
      <td>5986</td>
      <td>6000</td>
      <td>...</td>
      <td>NaN</td>
      <td>44.0</td>
      <td>NaN</td>
      <td>60.0</td>
      <td>OAPA</td>
      <td>12 Jan 2018</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Real-Time Distributed Control of Battery Energ...</td>
      <td>Y. Xu; J. Hu; W. Gu; W. Su; W. Liu</td>
      <td>SYSU-CMU Joint Institute of Engineering, SYSU-...</td>
      <td>IEEE Transactions on Smart Grid</td>
      <td>19 Apr 2018</td>
      <td>2018</td>
      <td>9</td>
      <td>3.0</td>
      <td>1580</td>
      <td>1589</td>
      <td>...</td>
      <td>NaN</td>
      <td>44.0</td>
      <td>NaN</td>
      <td>34.0</td>
      <td>IEEE</td>
      <td>27 Jul 2016</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>14</th>
      <td>A Coordinated Frequency Regulation Framework B...</td>
      <td>U. Akram; M. Khalid</td>
      <td>Electrical Engineering Department, King Fahd U...</td>
      <td>IEEE Access</td>
      <td>5 Mar 2018</td>
      <td>2018</td>
      <td>6</td>
      <td>NaN</td>
      <td>7310</td>
      <td>7320</td>
      <td>...</td>
      <td>NaN</td>
      <td>43.0</td>
      <td>NaN</td>
      <td>50.0</td>
      <td>OAPA</td>
      <td>22 Dec 2017</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>15</th>
      <td>A Computationally Efficient Optimization Appro...</td>
      <td>A. Das; Z. Ni</td>
      <td>Electrical Engineering and Computer Science De...</td>
      <td>IEEE Transactions on Smart Grid</td>
      <td>18 Oct 2018</td>
      <td>2018</td>
      <td>9</td>
      <td>6.0</td>
      <td>6489</td>
      <td>6499</td>
      <td>...</td>
      <td>NaN</td>
      <td>39.0</td>
      <td>NaN</td>
      <td>49.0</td>
      <td>IEEE</td>
      <td>8 Jun 2017</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>16</th>
      <td>Optimization of Battery Energy Storage to Impr...</td>
      <td>Y. Zhu; C. Liu; K. Sun; D. Shi; Z. Wang</td>
      <td>Department of EECS, University of Tennessee, K...</td>
      <td>IEEE Transactions on Sustainable Energy</td>
      <td>19 Jun 2019</td>
      <td>2019</td>
      <td>10</td>
      <td>3.0</td>
      <td>1015</td>
      <td>1024</td>
      <td>...</td>
      <td>NaN</td>
      <td>38.0</td>
      <td>NaN</td>
      <td>33.0</td>
      <td>IEEE</td>
      <td>23 Jul 2018</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Real-Time Coordinated Voltage Support With Bat...</td>
      <td>J. Krata; T. K. Saha</td>
      <td>School of Information Technology and Electrica...</td>
      <td>IEEE Transactions on Smart Grid</td>
      <td>22 Apr 2019</td>
      <td>2019</td>
      <td>10</td>
      <td>3.0</td>
      <td>3486</td>
      <td>3497</td>
      <td>...</td>
      <td>NaN</td>
      <td>34.0</td>
      <td>NaN</td>
      <td>45.0</td>
      <td>IEEE</td>
      <td>20 Apr 2018</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>18</th>
      <td>A Proactive and Survivability-Constrained Oper...</td>
      <td>A. Hussain; V. Bui; H. Kim</td>
      <td>Department of Electrical Engineering, Incheon ...</td>
      <td>IEEE Access</td>
      <td>18 Dec 2018</td>
      <td>2018</td>
      <td>6</td>
      <td>NaN</td>
      <td>75495</td>
      <td>75507</td>
      <td>...</td>
      <td>NaN</td>
      <td>32.0</td>
      <td>NaN</td>
      <td>33.0</td>
      <td>OAPA</td>
      <td>27 Nov 2018</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>19</th>
      <td>A Stochastic Optimization Method for Planning ...</td>
      <td>F. Conte; S. Massucco; M. Saviozzi; F. Silvestro</td>
      <td>Dipartimento di Ingegneria Navale, Elettrica, ...</td>
      <td>IEEE Transactions on Sustainable Energy</td>
      <td>19 Jun 2018</td>
      <td>2018</td>
      <td>9</td>
      <td>3.0</td>
      <td>1188</td>
      <td>1197</td>
      <td>...</td>
      <td>NaN</td>
      <td>32.0</td>
      <td>NaN</td>
      <td>29.0</td>
      <td>IEEE</td>
      <td>20 Nov 2017</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>20</th>
      <td>Battery Energy Storage Models for Optimal Control</td>
      <td>D. M. Rosewater; D. A. Copp; T. A. Nguyen; R. ...</td>
      <td>Sandia National Laboratories, Albuquerque, NM,...</td>
      <td>IEEE Access</td>
      <td>19 Dec 2019</td>
      <td>2019</td>
      <td>7</td>
      <td>NaN</td>
      <td>178357</td>
      <td>178391</td>
      <td>...</td>
      <td>NaN</td>
      <td>31.0</td>
      <td>NaN</td>
      <td>145.0</td>
      <td>CCBY</td>
      <td>4 Dec 2019</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>21</th>
      <td>Multiobjective Optimization of Data-Driven Mod...</td>
      <td>L. Cai; J. Meng; D. -I. Stroe; J. Peng; G. Luo...</td>
      <td>Faculty of Computer Science and Engineering, X...</td>
      <td>IEEE Transactions on Power Electronics</td>
      <td>29 Jul 2020</td>
      <td>2020</td>
      <td>35</td>
      <td>11.0</td>
      <td>11855</td>
      <td>11864</td>
      <td>...</td>
      <td>NaN</td>
      <td>28.0</td>
      <td>NaN</td>
      <td>38.0</td>
      <td>IEEE</td>
      <td>16 Apr 2020</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>22</th>
      <td>Optimal Whole-Life-Cycle Planning of Battery E...</td>
      <td>Y. Zhang; Y. Xu; H. Yang; Z. Y. Dong; R. Zhang</td>
      <td>School of Electrical and Information Engineeri...</td>
      <td>IEEE Transactions on Sustainable Energy</td>
      <td>18 Sep 2020</td>
      <td>2020</td>
      <td>11</td>
      <td>4.0</td>
      <td>2077</td>
      <td>2086</td>
      <td>...</td>
      <td>NaN</td>
      <td>28.0</td>
      <td>NaN</td>
      <td>37.0</td>
      <td>IEEE</td>
      <td>18 Sep 2019</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>23</th>
      <td>Interval Optimization Based Coordination of De...</td>
      <td>B. Wang; C. Zhang; Z. Y. Dong</td>
      <td>School of Electrical Engineering and Telecommu...</td>
      <td>IEEE Transactions on Sustainable Energy</td>
      <td>18 Sep 2020</td>
      <td>2020</td>
      <td>11</td>
      <td>4.0</td>
      <td>2922</td>
      <td>2931</td>
      <td>...</td>
      <td>NaN</td>
      <td>24.0</td>
      <td>NaN</td>
      <td>34.0</td>
      <td>IEEE</td>
      <td>20 Mar 2020</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>24</th>
      <td>Optimal Operation Control for Multiple BESSs o...</td>
      <td>S. -K. Kim; J. -Y. Kim; K. -H. Cho; G. Byeon</td>
      <td>Smart Distribution Research Center, Korea Elec...</td>
      <td>IEEE Transactions on Power Systems</td>
      <td>20 Dec 2017</td>
      <td>2018</td>
      <td>33</td>
      <td>1.0</td>
      <td>803</td>
      <td>816</td>
      <td>...</td>
      <td>NaN</td>
      <td>24.0</td>
      <td>NaN</td>
      <td>24.0</td>
      <td>IEEE</td>
      <td>2 May 2017</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>25</th>
      <td>A Fully Decentralized Adaptive Droop Optimizat...</td>
      <td>N. Vazquez; S. S. Yu; T. K. Chau; T. Fernando;...</td>
      <td>Department of Electrical, Electronic and Compu...</td>
      <td>IEEE Transactions on Energy Conversion</td>
      <td>27 Feb 2019</td>
      <td>2019</td>
      <td>34</td>
      <td>1.0</td>
      <td>385</td>
      <td>395</td>
      <td>...</td>
      <td>NaN</td>
      <td>23.0</td>
      <td>NaN</td>
      <td>27.0</td>
      <td>IEEE</td>
      <td>26 Oct 2018</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>26</th>
      <td>A Multiagent-Based Hierarchical Energy Managem...</td>
      <td>W. Jiang; K. Yang; J. Yang; R. Mao; N. Xue; Z....</td>
      <td>College of Electronics and Information Enginee...</td>
      <td>IEEE Access</td>
      <td>3 Dec 2019</td>
      <td>2019</td>
      <td>7</td>
      <td>NaN</td>
      <td>169931</td>
      <td>169945</td>
      <td>...</td>
      <td>NaN</td>
      <td>22.0</td>
      <td>NaN</td>
      <td>34.0</td>
      <td>CCBY</td>
      <td>25 Nov 2019</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>27</th>
      <td>Optimal Design of an Islanded Microgrid With L...</td>
      <td>B. Mohandes; S. Acharya; M. S. E. Moursi; A. S...</td>
      <td>Electrical Engineering and Computer Science De...</td>
      <td>IEEE Transactions on Power Systems</td>
      <td>17 Jun 2020</td>
      <td>2020</td>
      <td>35</td>
      <td>4.0</td>
      <td>2642</td>
      <td>2657</td>
      <td>...</td>
      <td>NaN</td>
      <td>22.0</td>
      <td>NaN</td>
      <td>52.0</td>
      <td>IEEE</td>
      <td>28 Jan 2020</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>28</th>
      <td>Energy management and operational control meth...</td>
      <td>X. Li; S. Wang</td>
      <td>State Key Laboratory of Control and Operation ...</td>
      <td>CSEE Journal of Power and Energy Systems</td>
      <td>4 Oct 2021</td>
      <td>2021</td>
      <td>7</td>
      <td>5.0</td>
      <td>1026</td>
      <td>1040</td>
      <td>...</td>
      <td>NaN</td>
      <td>21.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>13 Jun 2019</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>CSEE</td>
      <td>CSEE Journals</td>
    </tr>
    <tr>
      <th>29</th>
      <td>Optimal Sizing and Operation of Battery Energy...</td>
      <td>I. N. Moghaddam; B. Chowdhury; M. Doostan</td>
      <td>Electrical and Computer Engineering Department...</td>
      <td>IEEE Transactions on Sustainable Energy</td>
      <td>19 Jun 2019</td>
      <td>2019</td>
      <td>10</td>
      <td>3.0</td>
      <td>1184</td>
      <td>1193</td>
      <td>...</td>
      <td>NaN</td>
      <td>21.0</td>
      <td>NaN</td>
      <td>37.0</td>
      <td>IEEE</td>
      <td>6 Aug 2018</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>30</th>
      <td>Battery Energy Storage State-of-Charge Forecas...</td>
      <td>D. Rosewater; S. Ferreira; D. Schoenwald; J. H...</td>
      <td>Energy Storage Technologies and Systems, Sandi...</td>
      <td>IEEE Transactions on Smart Grid</td>
      <td>22 Apr 2019</td>
      <td>2019</td>
      <td>10</td>
      <td>3.0</td>
      <td>2453</td>
      <td>2462</td>
      <td>...</td>
      <td>NaN</td>
      <td>20.0</td>
      <td>NaN</td>
      <td>29.0</td>
      <td>OAPA</td>
      <td>25 Jan 2018</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>31</th>
      <td>Economic Operation Optimization for 2nd Use Ba...</td>
      <td>S. Jinlei; P. Lei; L. Ruihang; M. Qian; T. Chu...</td>
      <td>School of Automation, Nanjing University of Sc...</td>
      <td>IEEE Access</td>
      <td>11 Apr 2019</td>
      <td>2019</td>
      <td>7</td>
      <td>NaN</td>
      <td>41852</td>
      <td>41859</td>
      <td>...</td>
      <td>NaN</td>
      <td>20.0</td>
      <td>NaN</td>
      <td>22.0</td>
      <td>OAPA</td>
      <td>1 Mar 2019</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>32</th>
      <td>Improved Battery Storage Valuation Through Deg...</td>
      <td>B. Foggo; N. Yu</td>
      <td>University of California, Riverside, CA, USA; ...</td>
      <td>IEEE Transactions on Smart Grid</td>
      <td>21 Oct 2018</td>
      <td>2018</td>
      <td>9</td>
      <td>6.0</td>
      <td>5721</td>
      <td>5732</td>
      <td>...</td>
      <td>NaN</td>
      <td>20.0</td>
      <td>NaN</td>
      <td>26.0</td>
      <td>IEEE</td>
      <td>2 May 2017</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>33</th>
      <td>Robust Control Scheme for Distributed Battery ...</td>
      <td>A. Oshnoei; M. Kheradmandi; S. M. Muyeen</td>
      <td>Faculty of Electrical Engineering, Shahid Behe...</td>
      <td>IEEE Transactions on Power Systems</td>
      <td>26 Oct 2020</td>
      <td>2020</td>
      <td>35</td>
      <td>6.0</td>
      <td>4781</td>
      <td>4791</td>
      <td>...</td>
      <td>NaN</td>
      <td>20.0</td>
      <td>NaN</td>
      <td>23.0</td>
      <td>IEEE</td>
      <td>27 May 2020</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>34</th>
      <td>Reinforcement Learning-Based Distributed BESS ...</td>
      <td>M. Al-Saffar; P. Musilek</td>
      <td>Department of Electrical and Computer Engineer...</td>
      <td>IEEE Transactions on Smart Grid</td>
      <td>19 Jun 2020</td>
      <td>2020</td>
      <td>11</td>
      <td>4.0</td>
      <td>2980</td>
      <td>2994</td>
      <td>...</td>
      <td>NaN</td>
      <td>19.0</td>
      <td>NaN</td>
      <td>45.0</td>
      <td>IEEE</td>
      <td>6 Feb 2020</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>35</th>
      <td>Design and Power Management of Solar Powered E...</td>
      <td>T. S. Biya; M. R. Sindhu</td>
      <td>Department of Electrical and Electronics Engin...</td>
      <td>2019 3rd International conference on Electroni...</td>
      <td>2 Sep 2019</td>
      <td>2019</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>815</td>
      <td>820</td>
      <td>...</td>
      <td>NaN</td>
      <td>18.0</td>
      <td>NaN</td>
      <td>12.0</td>
      <td>NaN</td>
      <td>2 Sep 2019</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Conferences</td>
    </tr>
    <tr>
      <th>36</th>
      <td>Sizing Battery Energy Storage Systems: Using M...</td>
      <td>J. J. Kelly; P. G. Leahy</td>
      <td>School of Engineering, and the Marine and Rene...</td>
      <td>IEEE Transactions on Sustainable Energy</td>
      <td>18 Sep 2020</td>
      <td>2020</td>
      <td>11</td>
      <td>4.0</td>
      <td>2305</td>
      <td>2314</td>
      <td>...</td>
      <td>NaN</td>
      <td>18.0</td>
      <td>NaN</td>
      <td>35.0</td>
      <td>IEEE</td>
      <td>20 Nov 2019</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>37</th>
      <td>An Integrated Energy Management Approach for t...</td>
      <td>G. Mohy-ud-din; D. H. Vu; K. M. Muttaqi; D. Su...</td>
      <td>Australian Power Quality and Reliability Centr...</td>
      <td>IEEE Transactions on Industry Applications</td>
      <td>13 Mar 2020</td>
      <td>2020</td>
      <td>56</td>
      <td>2.0</td>
      <td>1062</td>
      <td>1073</td>
      <td>...</td>
      <td>NaN</td>
      <td>17.0</td>
      <td>NaN</td>
      <td>45.0</td>
      <td>IEEE</td>
      <td>7 Jan 2020</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>38</th>
      <td>Enhancement of a Small Power System Performanc...</td>
      <td>M. E. Lotfy; T. Senjyu; M. A. Farahat; A. F. A...</td>
      <td>Department of Electrical Power and Machines, F...</td>
      <td>IEEE Access</td>
      <td>15 May 2017</td>
      <td>2017</td>
      <td>5</td>
      <td>NaN</td>
      <td>6212</td>
      <td>6224</td>
      <td>...</td>
      <td>NaN</td>
      <td>17.0</td>
      <td>NaN</td>
      <td>40.0</td>
      <td>OAPA</td>
      <td>12 Apr 2017</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>39</th>
      <td>Hierarchical Optimal Allocation of Battery Ene...</td>
      <td>Y. Zheng; Y. Song; A. Huang; D. J. Hill</td>
      <td>School of Electrical and Information Engineeri...</td>
      <td>IEEE Transactions on Sustainable Energy</td>
      <td>19 Jun 2020</td>
      <td>2020</td>
      <td>11</td>
      <td>3.0</td>
      <td>1911</td>
      <td>1921</td>
      <td>...</td>
      <td>NaN</td>
      <td>17.0</td>
      <td>NaN</td>
      <td>24.0</td>
      <td>IEEE</td>
      <td>9 Oct 2019</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>40</th>
      <td>Optimal Sizing of Battery Energy Storage for G...</td>
      <td>U. T. Salman; F. S. Al-Ismail; M. Khalid</td>
      <td>Electrical Engineering Department, King Fahd U...</td>
      <td>IEEE Access</td>
      <td>29 May 2020</td>
      <td>2020</td>
      <td>8</td>
      <td>NaN</td>
      <td>91129</td>
      <td>91138</td>
      <td>...</td>
      <td>NaN</td>
      <td>17.0</td>
      <td>NaN</td>
      <td>34.0</td>
      <td>CCBY</td>
      <td>5 May 2020</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>41</th>
      <td>Optimal Sizing of Multiple Renewable Energy Re...</td>
      <td>M. Ahmadi; M. E. Lotfy; R. Shigenobu; A. M. Ho...</td>
      <td>Faculty of Engineering, University of the Ryuk...</td>
      <td>IEEE Systems Journal</td>
      <td>23 Aug 2019</td>
      <td>2019</td>
      <td>13</td>
      <td>3.0</td>
      <td>3026</td>
      <td>3037</td>
      <td>...</td>
      <td>NaN</td>
      <td>17.0</td>
      <td>NaN</td>
      <td>29.0</td>
      <td>IEEE</td>
      <td>6 Jun 2019</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>42</th>
      <td>Peer-to-peer market clearing framework for DER...</td>
      <td>M. Khorasany; Y. Mishra; G. Ledwich</td>
      <td>School of Electrical Engineering and Computer ...</td>
      <td>2017 IEEE PES Innovative Smart Grid Technologi...</td>
      <td>18 Jan 2018</td>
      <td>2017</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1</td>
      <td>6</td>
      <td>...</td>
      <td>NaN</td>
      <td>17.0</td>
      <td>NaN</td>
      <td>20.0</td>
      <td>NaN</td>
      <td>18 Jan 2018</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Conferences</td>
    </tr>
    <tr>
      <th>43</th>
      <td>Power Management Approach to Minimize Battery ...</td>
      <td>C. Nguyen; H. Lee</td>
      <td>École de technologie supérieure, University of...</td>
      <td>IEEE Transactions on Industry Applications</td>
      <td>22 Sep 2017</td>
      <td>2017</td>
      <td>53</td>
      <td>5.0</td>
      <td>4843</td>
      <td>4854</td>
      <td>...</td>
      <td>NaN</td>
      <td>17.0</td>
      <td>NaN</td>
      <td>32.0</td>
      <td>IEEE</td>
      <td>10 May 2017</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>44</th>
      <td>Power Management of Microgrids Including PHEVs...</td>
      <td>E. Fouladi; H. R. Baghaee; M. Bagheri; G. B. G...</td>
      <td>Department of Electrical Engineering, Amirkabi...</td>
      <td>IEEE Transactions on Industry Applications</td>
      <td>18 Sep 2020</td>
      <td>2020</td>
      <td>56</td>
      <td>5.0</td>
      <td>5299</td>
      <td>5307</td>
      <td>...</td>
      <td>NaN</td>
      <td>16.0</td>
      <td>NaN</td>
      <td>40.0</td>
      <td>IEEE</td>
      <td>21 Jul 2020</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>45</th>
      <td>Voltage Security Constrained Stochastic Progra...</td>
      <td>S. M. Mohseni-Bonab; I. Kamwa; A. Moeini; A. R...</td>
      <td>Electrical Engineering Department, Université ...</td>
      <td>IEEE Transactions on Sustainable Energy</td>
      <td>17 Dec 2019</td>
      <td>2020</td>
      <td>11</td>
      <td>1.0</td>
      <td>391</td>
      <td>404</td>
      <td>...</td>
      <td>NaN</td>
      <td>16.0</td>
      <td>NaN</td>
      <td>44.0</td>
      <td>IEEE</td>
      <td>9 Jan 2019</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>46</th>
      <td>Power Quality Improvement in Microgrids Under ...</td>
      <td>J. Alshehri; M. Khalid</td>
      <td>Electrical Engineering Department, King Fahd U...</td>
      <td>IEEE Access</td>
      <td>21 Oct 2019</td>
      <td>2019</td>
      <td>7</td>
      <td>NaN</td>
      <td>147314</td>
      <td>147326</td>
      <td>...</td>
      <td>NaN</td>
      <td>15.0</td>
      <td>NaN</td>
      <td>45.0</td>
      <td>CCBY</td>
      <td>8 Oct 2019</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>47</th>
      <td>Stratified Optimization Strategy Used for Rest...</td>
      <td>J. Li; H. You; J. Qi; M. Kong; S. Zhang; H. Zhang</td>
      <td>Key Laboratory of Modern Power System Simulati...</td>
      <td>IEEE Access</td>
      <td>16 Sep 2019</td>
      <td>2019</td>
      <td>7</td>
      <td>NaN</td>
      <td>127339</td>
      <td>127352</td>
      <td>...</td>
      <td>NaN</td>
      <td>15.0</td>
      <td>NaN</td>
      <td>37.0</td>
      <td>CCBY</td>
      <td>27 Aug 2019</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>48</th>
      <td>A Small-Scale Prototype for the Optimization o...</td>
      <td>G. Barchi; G. Miori; D. Moser; S. Papantoniou</td>
      <td>Institute for Renewable Energy - EURAC Researc...</td>
      <td>2018 IEEE International Conference on Environm...</td>
      <td>18 Oct 2018</td>
      <td>2018</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1</td>
      <td>5</td>
      <td>...</td>
      <td>NaN</td>
      <td>14.0</td>
      <td>NaN</td>
      <td>16.0</td>
      <td>NaN</td>
      <td>18 Oct 2018</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Conferences</td>
    </tr>
    <tr>
      <th>49</th>
      <td>Combined HVAC and Battery Scheduling for Deman...</td>
      <td>D. T. Vedullapalli; R. Hadidi; B. Schroeder</td>
      <td>Department of Electrical and Computer Engineer...</td>
      <td>IEEE Transactions on Industry Applications</td>
      <td>11 Nov 2019</td>
      <td>2019</td>
      <td>55</td>
      <td>6.0</td>
      <td>7008</td>
      <td>7014</td>
      <td>...</td>
      <td>NaN</td>
      <td>14.0</td>
      <td>NaN</td>
      <td>15.0</td>
      <td>IEEE</td>
      <td>29 Aug 2019</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>50</th>
      <td>Minimization of building energy cost by optima...</td>
      <td>R. K. Bonthu; H. Pham; R. P. Aguilera; Q. P. Ha</td>
      <td>University of Technology Sydney, Ultimo, NSW 2...</td>
      <td>2017 20th International Conference on Electric...</td>
      <td>5 Oct 2017</td>
      <td>2017</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1</td>
      <td>6</td>
      <td>...</td>
      <td>NaN</td>
      <td>14.0</td>
      <td>NaN</td>
      <td>18.0</td>
      <td>NaN</td>
      <td>5 Oct 2017</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Conferences</td>
    </tr>
    <tr>
      <th>51</th>
      <td>A Fuzzy Optimization Model for Distribution Sy...</td>
      <td>K. Masteri; B. Venkatesh; W. Freitas</td>
      <td>Centre for Urban Energy, Ryerson University, T...</td>
      <td>IEEE Transactions on Power Systems</td>
      <td>22 Aug 2018</td>
      <td>2018</td>
      <td>33</td>
      <td>5.0</td>
      <td>5114</td>
      <td>5123</td>
      <td>...</td>
      <td>NaN</td>
      <td>13.0</td>
      <td>NaN</td>
      <td>30.0</td>
      <td>IEEE</td>
      <td>5 Apr 2018</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>52</th>
      <td>Energy Management System for a Grid-Connected ...</td>
      <td>U. B. Tayab; F. Yang; M. El-Hendawi; J. Lu</td>
      <td>Queensland Micro- and Nanotechnology Centre, S...</td>
      <td>2018 Australian &amp; New Zealand Control Conferen...</td>
      <td>10 Jan 2019</td>
      <td>2018</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>141</td>
      <td>144</td>
      <td>...</td>
      <td>NaN</td>
      <td>13.0</td>
      <td>NaN</td>
      <td>11.0</td>
      <td>NaN</td>
      <td>10 Jan 2019</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Conferences</td>
    </tr>
    <tr>
      <th>53</th>
      <td>Coordinated Control of OLTC and Energy Storage...</td>
      <td>T. Tewari; A. Mohapatra; S. Anand</td>
      <td>Department of Electrical Engineering, Indian I...</td>
      <td>IEEE Transactions on Sustainable Energy</td>
      <td>16 Dec 2020</td>
      <td>2021</td>
      <td>12</td>
      <td>1.0</td>
      <td>262</td>
      <td>272</td>
      <td>...</td>
      <td>NaN</td>
      <td>12.0</td>
      <td>NaN</td>
      <td>26.0</td>
      <td>IEEE</td>
      <td>28 Apr 2020</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>54</th>
      <td>Day-Ahead and Intra-Day Planning of Integrated...</td>
      <td>F. Conte; S. Massucco; G. Schiapparelli; F. Si...</td>
      <td>Dipartimento di Ingegneria Navale, Elettrica, ...</td>
      <td>IEEE Transactions on Sustainable Energy</td>
      <td>19 Jun 2020</td>
      <td>2020</td>
      <td>11</td>
      <td>3.0</td>
      <td>1797</td>
      <td>1806</td>
      <td>...</td>
      <td>NaN</td>
      <td>12.0</td>
      <td>NaN</td>
      <td>47.0</td>
      <td>IEEE</td>
      <td>13 Sep 2019</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>55</th>
      <td>Optimal Design of a Hybrid Energy Storage Syst...</td>
      <td>Y. Bai; J. Li; H. He; R. C. D. Santos; Q. Yang</td>
      <td>National Engineering Laboratory for Electric V...</td>
      <td>IEEE Access</td>
      <td>12 Aug 2020</td>
      <td>2020</td>
      <td>8</td>
      <td>NaN</td>
      <td>142148</td>
      <td>142158</td>
      <td>...</td>
      <td>NaN</td>
      <td>12.0</td>
      <td>NaN</td>
      <td>44.0</td>
      <td>CCBY</td>
      <td>3 Aug 2020</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
    <tr>
      <th>56</th>
      <td>Optimal design and operation of a remote hybri...</td>
      <td>F. Nejabatkhah; Y. W. Li; A. B. Nassif; T. Kang</td>
      <td>Department of Electrical and Computer Engineer...</td>
      <td>CPSS Transactions on Power Electronics and App...</td>
      <td>24 May 2018</td>
      <td>2018</td>
      <td>3</td>
      <td>1.0</td>
      <td>3</td>
      <td>13</td>
      <td>...</td>
      <td>NaN</td>
      <td>12.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>24 May 2018</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>CPSS</td>
      <td>CPSS Journals</td>
    </tr>
    <tr>
      <th>57</th>
      <td>Wind Power Economic Dispatch – Impact of Radia...</td>
      <td>M. Khalid</td>
      <td>Department of Electrical Engineering, King Fah...</td>
      <td>IEEE Access</td>
      <td>1 Apr 2019</td>
      <td>2019</td>
      <td>7</td>
      <td>NaN</td>
      <td>36819</td>
      <td>36832</td>
      <td>...</td>
      <td>NaN</td>
      <td>11.0</td>
      <td>NaN</td>
      <td>49.0</td>
      <td>OAPA</td>
      <td>19 Mar 2019</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IEEE</td>
      <td>IEEE Journals</td>
    </tr>
  </tbody>
</table>
<p>58 rows × 30 columns</p>
</div>




```python

```
