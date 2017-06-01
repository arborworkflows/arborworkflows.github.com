---
layout: page
title: Create a new Arbor app.
permalink: /build/addApp_makeFunction.html
---

## Step 3. Make a working Arbor function - more detail

This is a detailed version of Step 3 of [these instructions for making an Arbor app]({{ site.baseurl }}/build/addApp.html).

For this step you will need to use an Arbor instance that you have control over, like one that you have [installed yourself]({{ site.baseurl }}/usearbor/install/). If you want to post an Arbor App on one our [main AWS instances]({{ site.baseurl }}/usearbor/aws-instances/) then you will need to get it working locally first and then follow [this protocol](#).

Open your Arbor instance and log in.

![addApp1]({{ site.baseurl }}/assets/addApp/addApp-fig1.png)

We will create a new analysis in the collection called "functionsForArborApps," so set Arbor to save to that collection.

![addApp2]({{ site.baseurl }}/assets/addApp/addApp-fig2.png)

Now navigate to the "Analysis" tab.

![addApp3]({{ site.baseurl }}/assets/addApp/addApp-fig3.png)

Create a new function called "makeSimmap-app."

![addApp4]({{ site.baseurl }}/assets/addApp/addApp-fig4.png)

Set the language for this function to "R."

![addApp6]({{ site.baseurl }}/assets/addApp/addApp-fig6.png)

Now paste the code from step 2 into that window, and press save.

![addApp8]({{ site.baseurl }}/assets/addApp/addApp-fig8.png)

Next we need to set inputs and outputs.

![addApp9]({{ site.baseurl }}/assets/addApp/addApp-fig9.png)

The function takes three inputs: a tree, a table, and a column for analysis.

The tree:

![addApp10]({{ site.baseurl }}/assets/addApp/addApp-fig10.png)

The table:

![addApp11]({{ site.baseurl }}/assets/addApp/addApp-fig11.png)

The column to analyze:

![addApp12]({{ site.baseurl }}/assets/addApp/addApp-fig12.png)

Now, the output, an image:

![addApp13]({{ site.baseurl }}/assets/addApp/addApp-fig13.png)

All together these make three inputs and one output:

![addApp14]({{ site.baseurl }}/assets/addApp/addApp-fig13.png)

Test your function. You can use the data in the sampleData collection. After clicking "Setup and Run," set the following:

![addApp15]({{ site.baseurl }}/assets/addApp/addApp-fig15.png)

If it works you should see:

![addApp16]({{ site.baseurl }}/assets/addApp/addApp-fig16.png)

Now move to the visualization tab and find this output:

![addApp17]({{ site.baseurl }}/assets/addApp/addApp-fig17.png)

You should see the result:

![addApp18]({{ site.baseurl }}/assets/addApp/addApp-fig18.png)


Now, continue with the [original steps]({{ site.baseurl }}/build/addApp) - you are ready for step 4.
