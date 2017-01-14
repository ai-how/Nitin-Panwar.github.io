---
layout: post
title: Create Beautiful, Interactive data visualizations using Plotly in Python
published: true
---

** Follow these simple steps and your page refresh issue will be resolved.

  1. Install IIS url rewrite module.
  2. Add web.config file in your code base.
 
 <?xml version="1.0" encoding="utf-8"?> 
  <configuration>
      <system.webServer>
          <rewrite>
              <rules> 
                  <rule name="Main Rule" stopProcessing="true">
                      <match url=".*" />
                      <conditions logicalGrouping="MatchAll">
                          <add input="{REQUEST_FILENAME}" matchType="IsFile" negate="true" />                                 
                          <add input="{REQUEST_FILENAME}" matchType="IsDirectory" negate="true" />
                      </conditions>
                      <action type="Rewrite" url="/" />
                    </rule>
              </rules>
          </rewrite>
      </system.webServer>
  </configuration>




