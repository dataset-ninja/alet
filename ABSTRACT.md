The authors create the **ALET: Automated Labeling of Equipment and Tools Dataset** for detecting farming, gardening, office, stonemasonry, vehicle, woodworking, and workshop tools. The scenes in the dataset are snapshots of sophisticated environments with or without humans using the tools. The scenes the authors consider introduce several challenges for object detection, including the small scale of the tools, their articulated nature, occlusion, inter-class invariance, etc.

## Motivation

In the foreseeable future, robots and humans are anticipated to coexist and collaborate on tasks that are particularly challenging, exhausting, or ergonomically unfavorable for humans. This collaboration necessitates robots to possess capabilities for perceiving humans, tasks, and environments. A crucial aspect of this perceptual ability is the detection of objects, particularly tools. Regrettably, the robotics community has largely overlooked the significance of human-utilized tools. While some studies have delved into tool affordances or their detection and transfer, these investigations have primarily been conducted in isolated and constrained environments. Additionally, they have typically examined only a limited array of tools. Compounding this oversight, existing literature lacks exploration into tool detection, and there is currently no available dataset for this purpose.

## Dataset description

The authors focus on the detection of tools in realistic, cluttered environments where collaboration between humans and robots is expected. To be more specific, they study detection of tools in real work environments that are composed of many objects (tools) that look alike and that occlude each other. For this end, the authors first collect an extensive tool detection dataset composed of 49 tool categories. Then, they compare the widely used stateof-the-art object detectors on their dataset, as a baseline. The results suggest that detecting tools is very challenging owing to tools being too small and articulated, and bearing too much
inter-class similarity.

<img src="https://github.com/dataset-ninja/alet/assets/120389559/623e37a1-eb14-4209-8731-816be9ebbeab" alt="image" width="800">

<span style="font-size: smaller; font-style: italic;"> Samples from the METU-ALET dataset, illustrating the wide range of challenging scenes and tools that a robot is expected to recognize in a clutter, possible with human co-workers using the tools. Since annotations are too dense, only a small subset is displayed.</span>

The need for a dedicated dataset for tool detection arises from several distinct challenges:
* **Size Variation:** Many tools are small objects, presenting a challenge for standard object detectors optimized for detecting larger objects.
* **Articulation:** A significant number of tools are articulated, introducing additional complexities such as changes in viewpoint, scale, and illumination. Object detectors must accommodate these variations.
* **Cluttered Environments:** Tools are commonly used in environments with high clutter, leading to challenges related to clutter, occlusion, appearance, and illumination.
* **Low Inter-Class Differences:** Some tools exhibit minimal differences between classes, making it difficult for detectors to distinguish between similar objects, such as screwdrivers, chisels, and files, or putty knives and scrapers.

In ALET, the authors explore a range of 49 distinct tools categorized across six broad contexts or purposes: farming, gardening, office supplies, stonemasonry, vehicle maintenance, woodworking, and workshop tools. Notably, the dataset comprises the 20 most frequently occurring tools, including chisels, clamps, drills, files, gloves, hammers, mallets, meters, pens, pencils, planes, pliers, safety glasses, safety helmets, saws, screwdrivers, spades, tapes, trowels, and wrenches. Excluded from consideration are tools typically used in kitchen settings, as dedicated datasets already exist for this purpose. Additionally, the authors limited their focus to tools that can be readily grasped, pushed, or manipulated by a robot. Consequently, larger tools such as ladders, forklifts, and power tools exceeding the size of a handheld drill were omitted from the study.

The dataset comprises three distinct sets of images:
* **Web-collected Images:** The authors conducted web searches using specific keywords and usage descriptions, gathering royalty-free images from various online platforms including [Creativecommons](https://creativecommons.org/), [Wikicommons](https://commons.wikimedia.org/wiki/Main_Page), [Flickr](https://www.flickr.com/), [Pexels](https://www.pexels.com/), [Unsplash](https://unsplash.com/), [Shopify](https://www.shopify.com/), [Pixabay](https://pixabay.com/), [Everystock](https://www.everystockphoto.com/), and [Imfree](https://au.linkedin.com/company/imfree-inc.).
* **Author-Photographed Images:** Additionally, the authors captured photographs of office and workshop environments on their campus.
* **Synthetic Images:** To ensure a minimum of 200 instances for each tool, the authors created synthetic images. They achieved this by developing a simulation environment using the [Unity3D](https://unity.com/) platform and incorporating 3D models of the tools.

<img src="https://github.com/dataset-ninja/alet/assets/120389559/4e5ca04d-1707-41e1-9477-f420b0cf1011" alt="image" width="800">

<span style="font-size: smaller; font-style: italic;">Some examples from the Synthetic Images.</span>





