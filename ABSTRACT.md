The authors create the **METU-ALET: A Dataset for Tool Detection in the Wild** for detecting farming, gardening, office, stonemasonry, vehicle, woodworking, and workshop tools. The scenes in the dataset are snapshots of sophisticated environments with or without humans using the tools. The scenes the authors consider introduce several challenges for object detection, including the small scale of the tools, their articulated nature, occlusion, inter-class invariance, etc.

## Motivation

In the foreseeable future, robots and humans are anticipated to coexist and collaborate on tasks that are particularly challenging, exhausting, or ergonomically unfavorable for humans. This collaboration necessitates robots to possess capabilities for perceiving humans, tasks, and environments. A crucial aspect of this perceptual ability is the detection of objects, particularly tools. Regrettably, the robotics community has largely overlooked the significance of human-utilized tools. While some studies have delved into tool affordances or their detection and transfer, these investigations have primarily been conducted in isolated and constrained environments. Additionally, they have typically examined only a limited array of tools. Compounding this oversight, existing literature lacks exploration into tool detection, and there is currently no available dataset for this purpose.

## Dataset description

The authors focus on the detection of tools in realistic, cluttered environments where collaboration between humans and robots is expected. To be more specific, they study detection of tools in real work environments that are composed of many objects (tools) that look alike and that occlude each other. For this end, the authors first collect an extensive tool detection dataset composed of 49 tool categories. Then, they compare the widely used state-of-the-art object detectors on their dataset, as a baseline. The results suggest that detecting tools is very challenging owing to tools being too small and articulated, and bearing too much
inter-class similarity.

<img src="https://github.com/dataset-ninja/alet/assets/120389559/623e37a1-eb14-4209-8731-816be9ebbeab" alt="image" width="600">

<span style="font-size: smaller; font-style: italic;"> Samples from the METU-ALET dataset, illustrating the wide range of challenging scenes and tools that a robot is expected to recognize in a clutter, possible with human co-workers using the tools. Since annotations are too dense, only a small subset is displayed.</span>

The need for a dedicated dataset for tool detection arises from several distinct challenges:
* **Size Variation:** Many tools are small objects, presenting a challenge for standard object detectors optimized for detecting larger objects.
* **Articulation:** A significant number of tools are articulated, introducing additional complexities such as changes in viewpoint, scale, and illumination. Object detectors must accommodate these variations.
* **Cluttered Environments:** Tools are commonly used in environments with high clutter, leading to challenges related to clutter, occlusion, appearance, and illumination.
* **Low Inter-Class Differences:** Some tools exhibit minimal differences between classes, making it difficult for detectors to distinguish between similar objects, such as screwdrivers, chisels, and files, or putty knives and scrapers.

In ALET(Automated Labeling of Equipment and Tools), the authors explore a range of 49 distinct tools categorized across six broad contexts or purposes: farming, gardening, office supplies, stonemasonry, vehicle maintenance, woodworking, and workshop tools. Notably, the dataset comprises the 20 most frequently occurring tools, including chisels, clamps, drills, files, gloves, hammers, mallets, meters, pens, pencils, planes, pliers, safety glasses, safety helmets, saws, screwdrivers, spades, tapes, trowels, and wrenches. Excluded from consideration are tools typically used in kitchen settings, as dedicated datasets already exist for this purpose. Additionally, the authors limited their focus to tools that can be readily grasped, pushed, or manipulated by a robot. Consequently, larger tools such as ladders, forklifts, and power tools exceeding the size of a handheld drill were omitted from the study.

The dataset comprises three distinct sets of images:
* **Web-collected Images:** The authors conducted web searches using specific keywords and usage descriptions, gathering royalty-free images from various online platforms including [Creativecommons](https://creativecommons.org/), [Wikicommons](https://commons.wikimedia.org/wiki/Main_Page), [Flickr](https://www.flickr.com/), [Pexels](https://www.pexels.com/), [Unsplash](https://unsplash.com/), [Shopify](https://www.shopify.com/), [Pixabay](https://pixabay.com/), [Everystock](https://www.everystockphoto.com/), and [Imfree](https://au.linkedin.com/company/imfree-inc.).
* **Author-Photographed Images:** Additionally, the authors captured photographs of office and workshop environments on their campus.
* **Synthetic Images:** To ensure a minimum of 200 instances for each tool, the authors created synthetic images. They achieved this by developing a simulation environment using the [Unity3D](https://unity.com/) platform and incorporating 3D models of the tools.

<img src="https://github.com/dataset-ninja/alet/assets/120389559/4e5ca04d-1707-41e1-9477-f420b0cf1011" alt="image" width="600">

<span style="font-size: smaller; font-style: italic;">Some examples from the Synthetic Images.</span>

For each scene to be generated, the following steps were followed:
**Scene Setup:** The authors constructed an environment resembling a room, featuring four walls and 10 assorted objects like chairs, sofas, corner pieces, and televisions placed in fixed positions. At the room's center, they introduced one of six different tables selected randomly from a range of 1 to 6. To enhance variability, they also scattered unrelated objects like mugs and bottles randomly throughout the scene.
**Camera Configuration:** The camera's position in each dimension (x, y, z) was determined by random sampling from a uniform distribution ranging from -3 to 3. The camera's viewing direction was oriented towards the center of the top surface of the table.
**Tool Placement:** For each scene, the authors randomly spawned a variable number of tools, N, ranging from 5 to 20, chosen randomly from a pool of 49 options. These tools were dropped onto the table from positions [x, y, z] randomly selected from a uniform distribution ranging from 0 to 1 above the table surface. The initial orientation of each tool, along each dimension, was sampled uniformly from 0 to 360 degrees.

For annotating the tools in the downloaded and the photographed images, the authors used the [VGG Image Annotation (VIA) tool](https://solutions.innodata.com/).

## Dataset statistics

The dataset includes 22,835 bounding boxes (BBs). For each tool category, there are more than 200 BBs, which is on an order similar to the widely used object detection datasets such as [PASCAL](http://host.robots.ox.ac.uk/pascal/VOC/). As shown in Table II, METUALET includes tools that appear small (area < 322), medium (322 < area < 962 ) and large (962 < area) – following the naming convention from [MS-COCO](https://cocodataset.org/).

| Subset       | Small BBs | Medium BBs | Large BBs | Total |
|--------------|-----------|------------|-----------|-------|
| Downloaded   | 809       | 4650       | 5661      | 11114 |
| Photographed | 13        | 309        | 443       | 765   |
| Synthesized  | 813       | 6934       | 3209      | 10956 |
| Total        | 1629      | 11893      | 9313      | 22835 |

<span style="font-size: smaller; font-style: italic;">The sizes of the bounding boxes (BB) of the annotated tools in the dataset.</span>

The dataset is composed of 2699 images in total, and on average, has size 1138 × 903. Although the number of images may appear low, the number of bounding boxes (22835) is sufficient since there are more than 200 BBs per tools, and the avg. number of BBs per image is rather large (6.6).

| Subset       | Cardinality | Avg. Resolution |
|--------------|-------------|-----------------|
| Downloaded   | 1870        | 924 × 786       |
| Photographed | 89          | 3663 × 3310     |
| Synthesized  | 740         | 1374 × 917      |
| Total/Avg    | 2699        | 1138 × 903      |

<span style="font-size: smaller; font-style: italic;">The cardinality and the resolution of the images in the dataset.</span>

