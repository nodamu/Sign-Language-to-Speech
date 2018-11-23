1. Use annotation_tool.py to generate annotation files in VOC xml format
2. When using annotation_tool.py draw box from top left
xml file must look like this else discard

<annotation>
  <folder>Dataset/images/0</folder>
  <filename>IMG_5360.JPG</filename>
  <segmented>0</segmented>
  <size>
    <width>100</width>
    <height>100</height>
    <depth>3</depth>
  </size>
  <object>
    <name>0</name>
    <pose>Unspecified</pose>
    <truncated>0</truncated>
    <difficult>0</difficult>
    <bndbox>
      <xmin>8</xmin>
      <ymin>14</ymin>
      <xmax>71</xmax>
      <ymax>93</ymax>
    </bndbox>
  </object>
</annotation>

3. You can use any annotation tool that you prefer but it must be in VOC format
4. Change obj to respective label of the dataset
5. Use gen_anchors.py to generate anchors for training