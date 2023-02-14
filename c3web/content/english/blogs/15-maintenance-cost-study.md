---
title: "Maintenance Cost Study"
date: 2020-03-14T15:40:24+06:00
# talks thumb
image : "images/projects/AC/SealAge.png"
draft: false
# description
description: "This is meta description"
weight: 15
---


### An Investigation of Queensland’s Central Highlands Road Maintenance Data.
<br>

#### Description - RMPC Data

* Ten years of data from 1996 to 2005
* Collected at segment level
* Costs per kilometre for maintenance under the RMPC. Indexed for inflation
* 39 links - between towns on a road
* Other information such as seal and pavement ages, and if the road surface is sealed or unsealed

<hr>
<figure>
  <img src="/images/projects/AC/OriginalDataHistograms.png" width="750"  />
  <figcaption>
      <h5>Original Data Histograms</h5>
  </figcaption>
</figure>
<hr>

#### Preliminary Data Analysis

* Explore Year 2000 data to better understand the complete data set
* Cost/km as response variable
* Log(e) transformations on cost/km, segment length & seal age
* Categorisation of pavement age

<hr>
<figure>
  <img src="/images/projects/AC/TransformedVariablesHistograms.png" width="750"  />
  <figcaption>
      <h5>Transformed Variables Histograms</h5>
  </figcaption>
</figure>

<hr>
<figure>
  <img src="/images/projects/AC/SurfaceType.png" width="750"  />
  <figcaption>
      <h5>Effect of the Surface Type on cost/km</h5>
  </figcaption>
</figure>
<hr>

<figure>
  <img src="/images/projects/AC/SegmentLengthEffect.png" width="750"  />
  <figcaption>
      <h5>Effect of the Segment Length on cost/km. <br>At &alpha;=5% costs/km <br>99% CI [-0.106, 0.001] &there4; no relationship to cost/km</h5>
  </figcaption>
</figure>
<hr>

<figure>
  <img src="/images/projects/AC/PavementAge.png" width="750"  />
  <figcaption>
      <h5>Effect of Pavement Age on cost/km. <br>Except categories 6 to 11.9 and <=1.9, cost/km appears to increase with increase in pavement age for sealed pavements (lower panel)
<br>Unsealed pavements costs do not vary much for older pavements (upper)
</h5>
  </figcaption>
</figure>
<hr>

<figure>
  <img src="/images/projects/AC/SealAgeEffect.png" width="750"  />
  <figcaption>
      <h5>
      Effect of sealed Age on cost/km. <br>Sealed segments only (78% of total) <br>At &alpha; = 5% costs/km increase by 11.4 &plusmn; 7.2% for each year increase in seal age
      </h5>
  </figcaption>
</figure>
<hr>

<figure>
  <img src="/images/projects/AC/TimeEffect.png" width="750"  />
  <figcaption>
      <h5>
      Effect of time on cost/km. <br>Cost/km indexed for inflation decreases with time
      </h5>
  </figcaption>
</figure>
<hr>

#### Fitted Model
| **Model** | **Df** | **Deviance**|**Residual<br>Df**| **Residual<br>Dev**| **Pf(Chi)**|
| :------- |:-------:|:-----------:|:----------------:|:------------------:|:----------:|
| Null     |         |             | 15635          | 23377                 |           |
| Year     |     9   |     309     | 15626          | 23607                 |     0.000 |
| Surface  |     1   |     278     | 15625          | 22790                 |     0.000 |
| Group    |     2   |     1847    | 15623          | 20943                 |     0.000 |
| Year:Pavtcat     |     60   |     440     | 15563          | 20502                 |     0.000 |

<figure>
  <img src="/images/projects/AC/PearsonResiduals.png" width="750"  />
  <figcaption>
      <h5>
      Check fit of model <br>Residuals appear to be approximately normally distributed
      </h5>
  </figcaption>
</figure>
<hr>

#### Conclusions reached
- A regression model can be fitted to predict the cost/km using the predictors
    - Year, surface type & seal group
    - Interaction between pavement age and year
- RMPC data comprises 3 distinct groups (in deceasing order of cost/km)
    - Group of links sealed between 1996 and 2005
    - Group of links that contain unsealed sections
    - Group of links sealed before 1996
