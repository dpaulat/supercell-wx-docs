NEXRAD Level 3
==============

Supercell Wx supports many NEXRAD Level 3 products. The majority of products are
loaded by the application, although some don't yet have rendering capabilities.
The table below indicates the level of support for each product. Each product is
defined in detail within Interface Control Documents published by the National
Weather Service:

* ICD for the RPG to Class 1 User: https://www.roc.noaa.gov/wsr88d/BuildInfo/Files.aspx
* ICD for SPG to AWIPS Class 1 User: https://www.roc.noaa.gov/spg/SPGDocumentation.aspx

.. raw:: html

    <div class="my-table-responsive">
      <table class="docutils align-default">
        <thead>
          <tr class="row-odd">
            <th class="head"><p>Code</p></th>
            <th class="head"><p>Product Name</p></th>
            <th class="head"><p>Product Category</p></th>
          </tr>
        </thead>
        <tbody>
          <tr class="row-even">
            <td><p>2</p></td>
            <td><p>General Status Message</p></td>
            <td class="scwx-unsupported"><p>GSM</p></td>
          </tr>
          <tr class="row-odd">
            <td><p>30</p></td>
            <td><p>Base Spectrum Width</p></td>
            <td class="scwx-supported"><p>NSW</p></td>
          </tr>
          <tr class="row-even">
            <td><p>31</p></td>
            <td><p>User Selectable Storm Total Precipitation</p></td>
            <td></td>
          </tr>
          <tr class="row-odd">
            <td><p>32</p></td>
            <td><p>Digital Hybrid Scan Reflectivity</p></td>
            <td class="scwx-partial-support"><p>DHR<a href="#table-footnotes">*</a></p></td>
          </tr>
          <tr class="row-even">
            <td><p>37</p></td>
            <td><p>Composite Reflectivity (124 nmi)</p></td>
            <td class="scwx-supported"><p>NCR</p></td>
          </tr>
          <tr class="row-odd">
            <td><p>38</p></td>
            <td><p>Composite Reflectivity (248 nmi)</p></td>
            <td class="scwx-partial-support"><p>NCZ<a href="#table-footnotes">*</a></p></td>
          </tr>
          <tr class="row-even">
            <td><p>41</p></td>
            <td><p>Echo Tops</p></td>
            <td class="scwx-supported"><p>NET</p></td>
          </tr>
          <tr class="row-odd">
            <td><p>48</p></td>
            <td><p>VAD Wind Profile</p></td>
            <td class="scwx-unsupported"><p>NVW</p></td>
          </tr>
          <tr class="row-even">
            <td><p>50</p></td>
            <td><p>Cross Section (Reflectivity)</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-odd">
            <td><p>51</p></td>
            <td><p>Cross Section (Velocity)</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-even">
            <td><p>56</p></td>
            <td><p>Storm Relative Mean Radial Velocity</p></td>
            <td class="scwx-supported"><p>N0S<br/>N1S<br/>N2S<br/>N3S</p></td>
          </tr>
          <tr class="row-odd">
            <td><p>57</p></td>
            <td><p>Vertically Integrated Liquid</p></td>
            <td class="scwx-supported"><p>NVL</p></td>
          </tr>
          <tr class="row-even">
            <td><p>58</p></td>
            <td><p>Storm Tracking Information</p></td>
            <td class="scwx-supported"><p>NST</p></td>
          </tr>
          <tr class="row-odd">
            <td><p>59</p></td>
            <td><p>Hail Index</p></td>
            <td class="scwx-unsupported"><p>NHI</p></td>
          </tr>
          <tr class="row-even">
            <td><p>61</p></td>
            <td><p>Tornado Vortex Signature</p></td>
            <td class="scwx-unsupported"><p>NTV</p></td>
          </tr>
          <tr class="row-odd">
            <td><p>62</p></td>
            <td><p>Storm Structure</p></td>
            <td class="scwx-unsupported"><p>NSS</p></td>
          </tr>
          <tr class="row-even">
            <td><p>65</p></td>
            <td><p>Layer Composite Reflectivity (Low Level)</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-odd">
            <td><p>66</p></td>
            <td><p>Layer Composite Reflectivity (Middle Level)</p></td>
            <td class="scwx-partial-support"><p>NML<a href="#table-footnotes">*</a></p></td>
          </tr>
          <tr class="row-even">
            <td><p>67</p></td>
            <td><p>Layer Composite Reflectivity - AP Removed</p></td>
            <td class="scwx-partial-support"><p>NLA<a href="#table-footnotes">*</a></p></td>
          </tr>
          <tr class="row-odd">
            <td><p>74</p></td>
            <td><p>Radar Coded Message</p></td>
            <td class="scwx-unsupported"><p>RCM</p></td>
          </tr>
          <tr class="row-even">
            <td><p>75</p></td>
            <td><p>Free Text Message</p></td>
            <td class="scwx-unsupported"><p>FTM</p></td>
          </tr>
          <tr class="row-odd">
            <td><p>77</p></td>
            <td><p>PUP Text Message</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-even">
            <td><p>78</p></td>
            <td><p>Surface Rainfall Accumulation (1 hr)</p></td>
            <td class="scwx-unsupported"><p>N1P</p></td>
          </tr>
          <tr class="row-odd">
            <td><p>79</p></td>
            <td><p>Surface Rainfall Accumulation (3 hr)</p></td>
            <td class="scwx-unsupported"><p>N3P</p></td>
          </tr>
          <tr class="row-even">
            <td><p>80</p></td>
            <td><p>Storm Total Rainfall Accumulation</p></td>
            <td class="scwx-unsupported"><p>NTP</p></td>
          </tr>
          <tr class="row-odd">
            <td><p>81</p></td>
            <td><p>Hourly Digital Precipitation Array</p></td>
            <td class="scwx-unsupported"><p>DPA</p></td>
          </tr>
          <tr class="row-even">
            <td><p>82</p></td>
            <td><p>Supplemental Precipitation Data</p></td>
            <td class="scwx-unsupported"><p>SPD</p></td>
          </tr>
          <tr class="row-odd">
            <td><p>84</p></td>
            <td><p>Velocity Azimuth Display</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-even">
            <td><p>86</p></td>
            <td><p>Cross Section Velocity</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-odd">
            <td><p>90</p></td>
            <td><p>Layer Composite Reflectivity (High Level)</p></td>
            <td class="scwx-partial-support"><p>NHL<a href="#table-footnotes">*</a></p></td>
          </tr>
          <tr class="row-even">
            <td><p>93</p></td>
            <td><p>ITWS Digital Base Velocity</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-odd">
            <td><p>94</p></td>
            <td><p>Base Reflectivity Data Array</p></td>
            <td class="scwx-supported"><p>NXQ<br/>NYQ<br/>NZQ<br/>N0Q<br/>NAQ<br/>N1Q<br/>NBQ<br/>N2Q<br/>N3Q</p></td>
          </tr>
          <tr class="row-even">
            <td><p>97</p></td>
            <td><p>Composite Reflectivity Edited for AP (124 nmi)</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-odd">
            <td><p>98</p></td>
            <td><p>Composite Reflectivity Edited for AP (248 nmi)</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-even">
            <td><p>99</p></td>
            <td><p>Base Velocity Data Array</p></td>
            <td class="scwx-supported"><p>NXU<br/>NYU<br/>NZU<br/>N0U<br/>NAU<br/>N1U<br/>NBU<br/>N2U<br/>N3U</p></td>
          </tr>
          <tr class="row-odd">
            <td><p>100</p></td>
            <td><p>Site Adaptable parameters for VAD Wind Profile</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-even">
            <td><p>101</p></td>
            <td><p>Storm Track Alphanumeric Block</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-odd">
            <td><p>102</p></td>
            <td><p>Hail Index Alphanumeric Block</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-even">
            <td><p>104</p></td>
            <td><p>TVS Alphanumeric Block</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-odd">
            <td><p>105</p></td>
            <td><p>Site Adaptable Parameters for Combined Shear</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-even">
            <td><p>107</p></td>
            <td><p>Surface Rainfall (1 hr) Alphanumeric Block</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-odd">
            <td><p>108</p></td>
            <td><p>Surface Rainfall (3 hr) Alphanumeric Block</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-even">
            <td><p>109</p></td>
            <td><p>Storm Total Rainfall Accumulation Alphanumeric Block</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-odd">
            <td><p>110</p></td>
            <td><p>Clutter Likelihood Reflectivity Alphanumeric Block</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-even">
            <td><p>111</p></td>
            <td><p>Clutter Likelihood Doppler Alphanumeric Block</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-odd">
            <td><p>113</p></td>
            <td><p>Power Removed Control Product</p></td>
            <td class="scwx-unsupported"><p>NXF<br/>NYF<br/>NZF<br/>N0F<br/>NAF<br/>N1F<br/>NBF<br/>N2F<br/>N3F</p></td>
          </tr>
          <tr class="row-even">
            <td><p>132</p></td>
            <td><p>Clutter Likelihood Reflectivity</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-odd">
            <td><p>133</p></td>
            <td><p>Clutter Likelihood Doppler</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-even">
            <td><p>134</p></td>
            <td><p>High Resolution VIL</p></td>
            <td class="scwx-supported"><p>DVL</p></td>
          </tr>
          <tr class="row-odd">
            <td><p>135</p></td>
            <td><p>Enhanced Echo Tops</p></td>
            <td class="scwx-supported"><p>EET</p></td>
          </tr>
          <tr class="row-even">
            <td><p>137</p></td>
            <td><p>User Selectable Layer Composite Reflectivity</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-odd">
            <td><p>138</p></td>
            <td><p>Digital Storm Total Precipitation</p></td>
            <td class="scwx-unsupported"><p>DSP</p></td>
          </tr>
          <tr class="row-even">
            <td><p>140</p></td>
            <td><p>Gust Front MIGFA</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-odd">
            <td><p>141</p></td>
            <td><p>Mesocyclone Detection</p></td>
            <td class="scwx-unsupported"><p>NMD</p></td>
          </tr>
          <tr class="row-even">
            <td><p>143</p></td>
            <td><p>Tornado Vortex Signature Rapid Update</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-odd">
            <td><p>144</p></td>
            <td><p>One-hour Snow Water Equivalent</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-even">
            <td><p>145</p></td>
            <td><p>One-hour Snow Depth</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-odd">
            <td><p>146</p></td>
            <td><p>Storm Total Snow Water Equivalent</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-even">
            <td><p>147</p></td>
            <td><p>Storm Total Snow Depth</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-odd">
            <td><p>149</p></td>
            <td><p>Digital Mesocyclone Detection</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-even">
            <td><p>150</p></td>
            <td><p>User Selectable Snow Water Equivalent</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-odd">
            <td><p>151</p></td>
            <td><p>User Selectable Snow Depth</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-even">
            <td><p>152</p></td>
            <td><p>Archive III Status Product</p></td>
            <td class="scwx-unsupported"><p>RSL</p></td>
          </tr>
          <tr class="row-odd">
            <td><p>153</p></td>
            <td><p>Super Resolution Reflectivity Data Array</p></td>
            <td class="scwx-supported"><p>NXB<br/>NYB<br/>NZB<br/>N0B<br/>NAB<br/>N1B<br/>NBB<br/>N2B<br/>N3B</p></td>
          </tr>
          <tr class="row-even">
            <td><p>154</p></td>
            <td><p>Super Resolution Velocity Data Array</p></td>
            <td class="scwx-supported"><p>NXG<br/>NYG<br/>NZG<br/>N0G<br/>NAG<br/>N1G<br/>NBU<br/>N2U<br/>N3U</p></td>
          </tr>
          <tr class="row-odd">
            <td><p>155</p></td>
            <td><p>Super Resolution Spectrum Width Data Array</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-even">
            <td><p>159</p></td>
            <td><p>Digital Differential Reflectivity</p></td>
            <td class="scwx-supported"><p>NXX<br/>NYX<br/>NZX<br/>N0X<br/>NAX<br/>N1X<br/>NBX<br/>N2X<br/>N3X</p></td>
          </tr>
          <tr class="row-odd">
            <td><p>161</p></td>
            <td><p>Digital Correlation Coefficient</p></td>
            <td class="scwx-supported"><p>NXC<br/>NYC<br/>NZC<br/>N0C<br/>NAC<br/>N1C<br/>NBC<br/>N2C<br/>N3C</p></td>
          </tr>
          <tr class="row-even">
            <td><p>163</p></td>
            <td><p>Digital Specific Differential Phase</p></td>
            <td class="scwx-supported"><p>NXK<br/>NYK<br/>NZK<br/>N0K<br/>NAK<br/>N1K<br/>NBK<br/>N2K<br/>N3K</p></td>
          </tr>
          <tr class="row-odd">
            <td><p>165</p></td>
            <td><p>Digital Hydrometeor Classification</p></td>
            <td class="scwx-supported"><p>NXH<br/>NYH<br/>NZH<br/>N0H<br/>NAH<br/>N1H<br/>NBH<br/>N2H<br/>N3H</p></td>
          </tr>
          <tr class="row-even">
            <td><p>166</p></td>
            <td><p>Melting Layer</p></td>
            <td class="scwx-unsupported"><p>NXM<br/>NYM<br/>NZM<br/>N0M<br/>NAM<br/>N1M<br/>NBM<br/>N2M<br/>N3M</p></td>
          </tr>
          <tr class="row-odd">
            <td><p>167</p></td>
            <td><p>Super Res Digital Correlation Coefficient</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-even">
            <td><p>168</p></td>
            <td><p>Super Res Digital Phi</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-odd">
            <td><p>169</p></td>
            <td><p>One Hour Accumulation</p></td>
            <td class="scwx-unsupported"><p>OHA</p></td>
          </tr>
          <tr class="row-even">
            <td><p>170</p></td>
            <td><p>Digital Accumulation Array</p></td>
            <td class="scwx-supported"><p>DAA<a href="#table-footnotes">‡</a></p></td>
          </tr>
          <tr class="row-odd">
            <td><p>171</p></td>
            <td><p>Storm Total Accumulation</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-even">
            <td><p>172</p></td>
            <td><p>Digital Storm Total Accumulation</p></td>
            <td class="scwx-supported"><p>DTA<a href="#table-footnotes">‡</a></p></td>
          </tr>
          <tr class="row-odd">
            <td><p>173</p></td>
            <td><p>Digital User-Selectable Accumulation</p></td>
            <td class="scwx-supported"><p>DU3<br/>DU6<a href="#table-footnotes">‡</a></p></td>
          </tr>
          <tr class="row-even">
            <td><p>174</p></td>
            <td><p>Digital One-Hour Difference Accumulation</p></td>
            <td class="scwx-partial-support"><p>DOD<a href="#table-footnotes">*&dagger;</a></p></td>
          </tr>
          <tr class="row-odd">
            <td><p>175</p></td>
            <td><p>Digital Storm Total Difference Accumulation</p></td>
            <td class="scwx-partial-support"><p>DSD<a href="#table-footnotes">*&dagger;</a></p></td>
          </tr>
          <tr class="row-even">
            <td><p>176</p></td>
            <td><p>Digital Instantaneous Precipitation Rate</p></td>
            <td class="scwx-unsupported"><p>DPR</p></td>
          </tr>
          <tr class="row-odd">
            <td><p>177</p></td>
            <td><p>Hybrid Hydrometeor Classification</p></td>
            <td class="scwx-supported"><p>HHC</p></td>
          </tr>
          <tr class="row-even">
            <td><p>178</p></td>
            <td><p>Icing Hazard Level</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-odd">
            <td><p>179</p></td>
            <td><p>Hail Hazard Layers</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-even">
            <td><p>180</p></td>
            <td><p>Base Reflectivity (48 nmi)</p></td>
            <td class="scwx-supported"><p>TZ0<br/>TZ1<br/>TZ2</p></td>
          </tr>
          <tr class="row-odd">
            <td><p>182</p></td>
            <td><p>Base Velocity</p></td>
            <td class="scwx-supported"><p>TV0<br/>TV1<br/>TV2</p></td>
          </tr>
          <tr class="row-even">
            <td><p>184</p></td>
            <td><p>Base Spectrum Width</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-odd">
            <td><p>186</p></td>
            <td><p>Base Reflectivity (225 nmi)</p></td>
            <td class="scwx-partial-support"><p>TZL<a href="#table-footnotes">*</a></p></td>
          </tr>
          <tr class="row-even">
            <td><p>193</p></td>
            <td><p>Super Resolution Digital Reflectivity Data-Quality-Edited</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-odd">
            <td><p>195</p></td>
            <td><p>Digital Reflectivity, DQA-Edited Data Array</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-even">
            <td><p>196</p></td>
            <td><p>Microburst AMDA</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-odd">
            <td><p>197</p></td>
            <td><p>Rain Rate Classification</p></td>
            <td><p></p></td>
          </tr>
          <tr class="row-even">
            <td><p>202</p></td>
            <td><p>Shift Change Checklist</p></td>
            <td><p></p></td>
          </tr>
        </tbody>
      </table>
    </div>

.. _table-footnotes:

| \* Supported with manual loading
| † Known color table issues
| ‡ Unit display disabled

Legend
------

.. raw:: html

    <div class="my-table-responsive">
      <table class="docutils align-default">
        <thead>
          <tr class="row-odd">
            <th class="head"><p>Color</p></th>
            <th class="head"><p>Description</p></th>
          </tr>
        </thead>
        <tbody>
          <tr class="row-even">
            <td class="scwx-supported"></td>
            <td><p>Full support</p></td>
          </tr>
          <tr class="row-odd">
            <td class="scwx-partial-support"></td>
            <td><p>Partial support</p></td>
          </tr>
          <tr class="row-even">
            <td class="scwx-unsupported"></td>
            <td><p>Unsupported</p></td>
          </tr>
        </tbody>
      </table>
    </div>
