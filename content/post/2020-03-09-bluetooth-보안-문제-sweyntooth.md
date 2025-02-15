---
title: Bluetooth 보안 문제 – SweynTooth
author: openmicrolab
type: post
date: 2020-03-09T01:16:17+00:00
url: /bluetooth-보안-문제-sweyntooth/
categories:
  - Bluetooth
tags:
  - bluetooth
  - security

---
블루투스 소프트웨어 스텍에서 발견된 문제들. 다수의 칩 벤더들의 SDK에 문제(<span id="textcolor3"><span class="ptmb8t-">deadlocks, crashes</span></span> and <span id="textcolor4"><span class="ptmb8t-">buffer overflows</span></span> or <span id="textcolor5"><span class="ptmb8t-">completely bypass</span> <span class="ptmb8t-">security</span></span>)가 있어서 패치가 제공되었다.

<div class="caption">
  <span class="id">Table 1: </span><span class="content">Vulnerabilities type and affected vendors</span>
</div>

<div class="tabular">
  <table id="TBL-2" class="tabular" cellspacing="0" cellpadding="0">
    <colgroup id="TBL-2-1g"> <col id="TBL-2-1" /></colgroup> <colgroup id="TBL-2-2g"> <col id="TBL-2-2" /></colgroup> <colgroup id="TBL-2-3g"> <col id="TBL-2-3" /></colgroup> <colgroup id="TBL-2-4g"> <col id="TBL-2-4" /></colgroup> <tr class="hline">
      <td>
        <hr />
      </td>
      
      <td>
        <hr />
      </td>
      
      <td>
        <hr />
      </td>
      
      <td>
        <hr />
      </td>
    </tr>
    
    <tr id="TBL-2-1-">
      <td id="TBL-2-1-1" class="td11">
        <span class="ptmbi8t-">Type</span>
      </td>
      
      <td id="TBL-2-1-2" class="td11">
        <div class="multicolumn">
          <span class="ptmbi8t-">Vulnerability Name</span>
        </div>
      </td>
      
      <td id="TBL-2-1-3" class="td11">
        <div class="multicolumn">
          <span class="ptmbi8t-">Affected Vendors</span>
        </div>
      </td>
      
      <td id="TBL-2-1-4" class="td11">
        <span class="ptmbi8t-">CVE</span>
      </td>
    </tr>
    
    <tr class="hline">
      <td>
        <hr />
      </td>
      
      <td>
        <hr />
      </td>
      
      <td>
        <hr />
      </td>
      
      <td>
        <hr />
      </td>
    </tr>
    
    <tr id="TBL-2-2-">
      <td id="TBL-2-2-1" class="td11">
        <div class="multirow">
          <span class="ptmb8t-">Crash</span>
        </div>
      </td>
      
      <td id="TBL-2-2-2" class="td11">
        <div class="multicolumn">
          <div class="multirow">
            Link Layer Length Overflow
          </div>
        </div>
      </td>
      
      <td id="TBL-2-2-3" class="td11">
        <div class="multicolumn">
          Cypress
        </div>
      </td>
      
      <td id="TBL-2-2-4" class="td11">
        <a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2019-16336" target="_blank" rel="noopener">CVE-2019-16336</a> (<a href="https://asset-group.github.io/disclosures/sweyntooth/disclosure.html#x1-110006.1">6.1</a>)
      </td>
    </tr>
    
    <tr id="TBL-2-3-">
      <td id="TBL-2-3-1" class="td11">
      </td>
      
      <td id="TBL-2-3-2" class="td11">
      </td>
      
      <td id="TBL-2-3-3" class="td11">
        <div class="multicolumn">
          NXP
        </div>
      </td>
      
      <td id="TBL-2-3-4" class="td11">
        <a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2019-17519" target="_blank" rel="noopener">CVE-2019-17519</a> (<a href="https://asset-group.github.io/disclosures/sweyntooth/disclosure.html#x1-110006.1">6.1</a>)
      </td>
    </tr>
    
    <tr id="TBL-2-4-">
      <td id="TBL-2-4-1" class="td11">
      </td>
    </tr>
    
    <tr class="cline">
      <td>
      </td>
      
      <td>
        <hr />
      </td>
      
      <td>
        <hr />
      </td>
      
      <td>
        <hr />
      </td>
    </tr>
    
    <tr id="TBL-2-5-">
      <td id="TBL-2-5-1" class="td11">
      </td>
      
      <td id="TBL-2-5-2" class="td11">
        Truncated L2CAP
      </td>
      
      <td id="TBL-2-5-3" class="td11">
        Dialog Semiconductors
      </td>
      
      <td id="TBL-2-5-4" class="td11">
        <a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2019-17517" target="_blank" rel="noopener">CVE-2019-17517</a> (<a href="https://asset-group.github.io/disclosures/sweyntooth/disclosure.html#x1-130006.3">6.3</a>)
      </td>
    </tr>
    
    <tr id="TBL-2-6-">
      <td id="TBL-2-6-1" class="td11">
      </td>
    </tr>
    
    <tr class="cline">
      <td>
      </td>
      
      <td>
        <hr />
      </td>
      
      <td>
        <hr />
      </td>
      
      <td>
        <hr />
      </td>
    </tr>
    
    <tr id="TBL-2-7-">
      <td id="TBL-2-7-1" class="td11">
      </td>
      
      <td id="TBL-2-7-2" class="td11">
        Silent Length Overflow
      </td>
      
      <td id="TBL-2-7-3" class="td11">
        Dialog Semiconductors
      </td>
      
      <td id="TBL-2-7-4" class="td11">
        <a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2019-17518" target="_blank" rel="noopener">CVE-2019-17518</a> (<a href="https://asset-group.github.io/disclosures/sweyntooth/disclosure.html#x1-140006.4">6.4</a>)
      </td>
    </tr>
    
    <tr id="TBL-2-8-">
      <td id="TBL-2-8-1" class="td11">
      </td>
    </tr>
    
    <tr class="cline">
      <td>
      </td>
      
      <td>
        <hr />
      </td>
      
      <td>
        <hr />
      </td>
      
      <td>
        <hr />
      </td>
    </tr>
    
    <tr id="TBL-2-9-">
      <td id="TBL-2-9-1" class="td11">
      </td>
      
      <td id="TBL-2-9-2" class="td11">
        Public Key Crash
      </td>
      
      <td id="TBL-2-9-3" class="td11">
        Texas Instruments
      </td>
      
      <td id="TBL-2-9-4" class="td11">
        <a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2019-17520" target="_blank" rel="noopener">CVE-2019-17520</a> (<a href="https://asset-group.github.io/disclosures/sweyntooth/disclosure.html#x1-160006.6">6.6</a>)
      </td>
    </tr>
    
    <tr id="TBL-2-10-">
      <td id="TBL-2-10-1" class="td11">
      </td>
    </tr>
    
    <tr class="cline">
      <td>
      </td>
      
      <td>
        <hr />
      </td>
      
      <td>
        <hr />
      </td>
      
      <td>
        <hr />
      </td>
    </tr>
    
    <tr id="TBL-2-11-">
      <td id="TBL-2-11-1" class="td11">
      </td>
      
      <td id="TBL-2-11-2" class="td11">
        Invalid L2CAP Fragment
      </td>
      
      <td id="TBL-2-11-3" class="td11">
        Microchip
      </td>
      
      <td id="TBL-2-11-4" class="td11">
        <a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2019-19195" target="_blank" rel="noopener">CVE-2019-19195</a> (<a href="https://asset-group.github.io/disclosures/sweyntooth/disclosure.html#x1-180006.8">6.8</a>)
      </td>
    </tr>
    
    <tr id="TBL-2-12-">
      <td id="TBL-2-12-1" class="td11">
      </td>
    </tr>
    
    <tr class="cline">
      <td>
      </td>
      
      <td>
        <hr />
      </td>
      
      <td>
        <hr />
      </td>
      
      <td>
        <hr />
      </td>
    </tr>
    
    <tr id="TBL-2-13-">
      <td id="TBL-2-13-1" class="td11">
      </td>
      
      <td id="TBL-2-13-2" class="td11">
        Key Size Overflow
      </td>
      
      <td id="TBL-2-13-3" class="td11">
        Telink Semiconductor
      </td>
      
      <td id="TBL-2-13-4" class="td11">
        <a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2019-19196" target="_blank" rel="noopener">CVE-2019-19196</a> (<a href="https://asset-group.github.io/disclosures/sweyntooth/disclosure.html#x1-190006.9">6.9</a>)
      </td>
    </tr>
    
    <tr class="hline">
      <td>
        <hr />
      </td>
      
      <td>
        <hr />
      </td>
      
      <td>
        <hr />
      </td>
      
      <td>
        <hr />
      </td>
    </tr>
    
    <tr id="TBL-2-14-">
      <td id="TBL-2-14-1" class="td11">
        <div class="multirow">
          <span class="ptmb8t-">Deadlock</span>
        </div>
      </td>
      
      <td id="TBL-2-14-2" class="td11">
        <div class="multirow">
          LLID Deadlock
        </div>
      </td>
      
      <td id="TBL-2-14-3" class="td11">
        <div class="multicolumn">
          Cypress
        </div>
      </td>
      
      <td id="TBL-2-14-4" class="td11">
        <a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2019-17061" target="_blank" rel="noopener">CVE-2019-17061</a> (<a href="https://asset-group.github.io/disclosures/sweyntooth/disclosure.html#x1-120006.2">6.2</a>)
      </td>
    </tr>
    
    <tr id="TBL-2-15-">
      <td id="TBL-2-15-1" class="td11">
      </td>
      
      <td id="TBL-2-15-2" class="td11">
      </td>
      
      <td id="TBL-2-15-3" class="td11">
        <div class="multicolumn">
          NXP
        </div>
      </td>
      
      <td id="TBL-2-15-4" class="td11">
        <a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2019-17060" target="_blank" rel="noopener">CVE-2019-17060</a> (<a href="https://asset-group.github.io/disclosures/sweyntooth/disclosure.html#x1-120006.2">6.2</a>)
      </td>
    </tr>
    
    <tr id="TBL-2-16-">
      <td id="TBL-2-16-1" class="td11">
      </td>
    </tr>
    
    <tr class="cline">
      <td>
      </td>
      
      <td>
        <hr />
      </td>
      
      <td>
        <hr />
      </td>
      
      <td>
        <hr />
      </td>
    </tr>
    
    <tr id="TBL-2-17-">
      <td id="TBL-2-17-1" class="td11">
      </td>
      
      <td id="TBL-2-17-2" class="td11">
        Sequential ATT Deadlock
      </td>
      
      <td id="TBL-2-17-3" class="td11">
        STMicroelectronics
      </td>
      
      <td id="TBL-2-17-4" class="td11">
        <a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2019-19192" target="_blank" rel="noopener">CVE-2019-19192</a> (<a href="https://asset-group.github.io/disclosures/sweyntooth/disclosure.html#x1-170006.7">6.7</a>)
      </td>
    </tr>
    
    <tr id="TBL-2-18-">
      <td id="TBL-2-18-1" class="td11">
      </td>
    </tr>
    
    <tr class="cline">
      <td>
      </td>
      
      <td>
        <hr />
      </td>
      
      <td>
        <hr />
      </td>
      
      <td>
        <hr />
      </td>
    </tr>
    
    <tr id="TBL-2-19-">
      <td id="TBL-2-19-1" class="td11">
      </td>
      
      <td id="TBL-2-19-2" class="td11">
        Invalid Connection Request
      </td>
      
      <td id="TBL-2-19-3" class="td11">
        Texas Instruments
      </td>
      
      <td id="TBL-2-19-4" class="td11">
        <a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2019-19193" target="_blank" rel="noopener">CVE-2019-19193</a> (<a href="https://asset-group.github.io/disclosures/sweyntooth/disclosure.html#x1-150006.5">6.5</a>)
      </td>
    </tr>
    
    <tr class="hline">
      <td>
        <hr />
      </td>
      
      <td>
        <hr />
      </td>
      
      <td>
        <hr />
      </td>
      
      <td>
        <hr />
      </td>
    </tr>
    
    <tr id="TBL-2-20-">
      <td id="TBL-2-20-1" class="td11">
        <span class="ptmb8t-">Security Bypass</span>
      </td>
      
      <td id="TBL-2-20-2" class="td11">
        Zero LTK Installation
      </td>
      
      <td id="TBL-2-20-3" class="td11">
        Telink Semiconductor
      </td>
      
      <td id="TBL-2-20-4" class="td11">
        <a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2019-19194" target="_blank" rel="noopener">CVE-2019-19194</a> (<a href="https://asset-group.github.io/disclosures/sweyntooth/disclosure.html#x1-200006.10">6.10</a>)
      </td>
    </tr>
    
    <tr class="hline">
      <td>
        <hr />
      </td>
      
      <td>
        <hr />
      </td>
      
      <td>
        <hr />
      </td>
    </tr>
  </table>
</div>

<div class="table row items-start justify-center">
  <div class="float">
    <div>
    </div>
    
    <div class="caption">
      <span class="id">Table 2: </span><span class="content">Vulnerabilities and SDK versions of the affected SoCs.* indicates extra affected SoCs reported by the vendor not tracked by our team.</span>
    </div>
    
    <div class="tabular">
      <table id="TBL-3" class="tabular" cellspacing="0" cellpadding="0">
        <colgroup id="TBL-3-1g"> <col id="TBL-3-1" /> <col id="TBL-3-2" /> <col id="TBL-3-3" /> <col id="TBL-3-4" /> <col id="TBL-3-5" /></colgroup> <tr class="hline">
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
        </tr>
        
        <tr id="TBL-3-1-">
          <td id="TBL-3-1-1" class="td11">
            <div class="multicolumn">
              <span class="ptmb8t-">Vuln.</span>
            </div>
          </td>
          
          <td id="TBL-3-1-2" class="td11">
            <div class="multicolumn">
              <span class="ptmbi8t-">SoC Vendor</span>
            </div>
          </td>
          
          <td id="TBL-3-1-3" class="td11">
            <div class="multicolumn">
              <span class="ptmbi8t-">SoC Model</span>
            </div>
          </td>
          
          <td id="TBL-3-1-4" class="td11">
            <span class="ptmbi8t-">SDK Ver.</span>
          </td>
          
          <td id="TBL-3-1-5" class="td11">
            <div class="multicolumn">
              <span class="ptmbi8t-">Qualification ID(s)</span>
            </div>
          </td>
        </tr>
        
        <tr class="hline">
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
        </tr>
        
        <tr id="TBL-3-2-">
          <td id="TBL-3-2-1" class="td11">
          </td>
          
          <td id="TBL-3-2-2" class="td11">
            <span class="ptmbi8t-">BLE Version 5.0/5.1</span>
          </td>
          
          <td id="TBL-3-2-3" class="td11">
          </td>
          
          <td id="TBL-3-2-4" class="td11">
            <div class="multicolumn">
            </div>
          </td>
          
          <td id="TBL-3-2-5" class="td11">
          </td>
        </tr>
        
        <tr id="TBL-3-3-">
          <td id="TBL-3-3-1" class="td11">
            <a href="https://asset-group.github.io/disclosures/sweyntooth/disclosure.html#x1-110006.1">6.1</a>,<a href="https://asset-group.github.io/disclosures/sweyntooth/disclosure.html#x1-120006.2">6.2</a>
          </td>
          
          <td id="TBL-3-3-2" class="td11">
            Cypress (PSoC 6)
          </td>
          
          <td id="TBL-3-3-3" class="td11">
            CYBLE-416045
          </td>
          
          <td id="TBL-3-3-4" class="td11">
            2.10
          </td>
          
          <td id="TBL-3-3-5" class="td11">
            99158
          </td>
        </tr>
        
        <tr id="TBL-3-4-">
          <td id="TBL-3-4-1" class="td11">
            <a href="https://asset-group.github.io/disclosures/sweyntooth/disclosure.html#x1-150006.5">6.5</a>,<a href="https://asset-group.github.io/disclosures/sweyntooth/disclosure.html#x1-160006.6">6.6</a>
          </td>
          
          <td id="TBL-3-4-2" class="td11">
            Texas Instruments
          </td>
          
          <td id="TBL-3-4-3" class="td11">
            CC2640R2
          </td>
          
          <td id="TBL-3-4-4" class="td11">
            3.30.00.20
          </td>
          
          <td id="TBL-3-4-5" class="td11">
            94079
          </td>
        </tr>
        
        <tr id="TBL-3-5-">
          <td id="TBL-3-5-1" class="td11">
            <a href="https://asset-group.github.io/disclosures/sweyntooth/disclosure.html#x1-190006.9">6.9</a>,<a href="https://asset-group.github.io/disclosures/sweyntooth/disclosure.html#x1-200006.10">6.10</a>
          </td>
          
          <td id="TBL-3-5-2" class="td11">
            Telink
          </td>
          
          <td id="TBL-3-5-3" class="td11">
            TLSR8258
          </td>
          
          <td id="TBL-3-5-4" class="td11">
            3.4.0
          </td>
          
          <td id="TBL-3-5-5" class="td11">
            92269, 136037
          </td>
        </tr>
        
        <tr id="TBL-3-6-">
          <td id="TBL-3-6-1" class="td11">
            <a href="https://asset-group.github.io/disclosures/sweyntooth/disclosure.html#x1-170006.7">6.7</a>
          </td>
          
          <td id="TBL-3-6-2" class="td11">
            STMicroelectronics
          </td>
          
          <td id="TBL-3-6-3" class="td11">
            WB55
          </td>
          
          <td id="TBL-3-6-4" class="td11">
            1.3.0
          </td>
          
          <td id="TBL-3-6-5" class="td11">
            111668
          </td>
        </tr>
        
        <tr id="TBL-3-7-">
          <td id="TBL-3-7-1" class="td11">
            <a href="https://asset-group.github.io/disclosures/sweyntooth/disclosure.html#x1-170006.7">6.7</a>
          </td>
          
          <td id="TBL-3-7-2" class="td11">
            STMicroelectroncis
          </td>
          
          <td id="TBL-3-7-3" class="td11">
            BlueNRG-2
          </td>
          
          <td id="TBL-3-7-4" class="td11">
            3.1.0
          </td>
          
          <td id="TBL-3-7-5" class="td11">
            87428, 106700, 94075
          </td>
        </tr>
        
        <tr id="TBL-3-8-">
          <td id="TBL-3-8-1" class="td11">
            <a href="https://asset-group.github.io/disclosures/sweyntooth/disclosure.html#x1-140006.4">6.4</a>
          </td>
          
          <td id="TBL-3-8-2" class="td11">
            Dialog
          </td>
          
          <td id="TBL-3-8-3" class="td11">
            DA1469X*
          </td>
          
          <td id="TBL-3-8-4" class="td11">
            10.0.6
          </td>
          
          <td id="TBL-3-8-5" class="td11">
            100899
          </td>
        </tr>
        
        <tr id="TBL-3-9-">
          <td id="TBL-3-9-1" class="td11">
            <a href="https://asset-group.github.io/disclosures/sweyntooth/disclosure.html#x1-130006.3">6.3</a>
          </td>
          
          <td id="TBL-3-9-2" class="td11">
            Dialog
          </td>
          
          <td id="TBL-3-9-3" class="td11">
            DA14585/6*
          </td>
          
          <td id="TBL-3-9-4" class="td11">
            6.0.12.1020
          </td>
          
          <td id="TBL-3-9-5" class="td11">
            91436
          </td>
        </tr>
        
        <tr class="hline">
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
        </tr>
        
        <tr id="TBL-3-10-">
          <td id="TBL-3-10-1" class="td11">
          </td>
          
          <td id="TBL-3-10-2" class="td11">
            <span class="ptmbi8t-">BLE Version 4.2</span>
          </td>
          
          <td id="TBL-3-10-3" class="td11">
          </td>
          
          <td id="TBL-3-10-4" class="td11">
          </td>
          
          <td id="TBL-3-10-5" class="td11">
          </td>
        </tr>
        
        <tr id="TBL-3-11-">
          <td id="TBL-3-11-1" class="td11">
            <a href="https://asset-group.github.io/disclosures/sweyntooth/disclosure.html#x1-110006.1">6.1</a>,<a href="https://asset-group.github.io/disclosures/sweyntooth/disclosure.html#x1-120006.2">6.2</a>
          </td>
          
          <td id="TBL-3-11-2" class="td11">
            Cypress (PSoC 4)
          </td>
          
          <td id="TBL-3-11-3" class="td11">
            CYBL11573
          </td>
          
          <td id="TBL-3-11-4" class="td11">
            3.60
          </td>
          
          <td id="TBL-3-11-5" class="td11">
            62243, 136808, 79697, 82951, 79480
          </td>
        </tr>
        
        <tr id="TBL-3-12-">
          <td id="TBL-3-12-1" class="td11">
            <a href="https://asset-group.github.io/disclosures/sweyntooth/disclosure.html#x1-110006.1">6.1</a>,<a href="https://asset-group.github.io/disclosures/sweyntooth/disclosure.html#x1-120006.2">6.2</a>
          </td>
          
          <td id="TBL-3-12-2" class="td11">
            NXP
          </td>
          
          <td id="TBL-3-12-3" class="td11">
            KW41Z
          </td>
          
          <td id="TBL-3-12-4" class="td11">
            2.2.1
          </td>
          
          <td id="TBL-3-12-5" class="td11">
            84040
          </td>
        </tr>
        
        <tr id="TBL-3-13-">
          <td id="TBL-3-13-1" class="td11">
            <a href="https://asset-group.github.io/disclosures/sweyntooth/disclosure.html#x1-140006.4">6.4</a>
          </td>
          
          <td id="TBL-3-13-2" class="td11">
            Dialog
          </td>
          
          <td id="TBL-3-13-3" class="td11">
            DA14680
          </td>
          
          <td id="TBL-3-13-4" class="td11">
            1.0.14.X
          </td>
          
          <td id="TBL-3-13-5" class="td11">
            87407, 84084, 71309, 75255
          </td>
        </tr>
        
        <tr class="hline">
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
        </tr>
        
        <tr id="TBL-3-14-">
          <td id="TBL-3-14-1" class="td11">
          </td>
          
          <td id="TBL-3-14-2" class="td11">
            <span class="ptmbi8t-">BLE Version 4.1</span>
          </td>
          
          <td id="TBL-3-14-3" class="td11">
          </td>
          
          <td id="TBL-3-14-4" class="td11">
          </td>
          
          <td id="TBL-3-14-5" class="td11">
          </td>
        </tr>
        
        <tr id="TBL-3-15-">
          <td id="TBL-3-15-1" class="td11">
            <a href="https://asset-group.github.io/disclosures/sweyntooth/disclosure.html#x1-150006.5">6.5</a>
          </td>
          
          <td id="TBL-3-15-2" class="td11">
            Texas Instruments
          </td>
          
          <td id="TBL-3-15-3" class="td11">
            CC2540
          </td>
          
          <td id="TBL-3-15-4" class="td11">
            1.5.0
          </td>
          
          <td id="TBL-3-15-5" class="td11">
            23454, 127418
          </td>
        </tr>
        
        <tr id="TBL-3-16-">
          <td id="TBL-3-16-1" class="td11">
            <a href="https://asset-group.github.io/disclosures/sweyntooth/disclosure.html#x1-130006.3">6.3</a>
          </td>
          
          <td id="TBL-3-16-2" class="td11">
            Dialog
          </td>
          
          <td id="TBL-3-16-3" class="td11">
            DA14580
          </td>
          
          <td id="TBL-3-16-4" class="td11">
            5.0.4
          </td>
          
          <td id="TBL-3-16-5" class="td11">
            83573
          </td>
        </tr>
        
        <tr id="TBL-3-17-">
          <td id="TBL-3-17-1" class="td11">
            <a href="https://asset-group.github.io/disclosures/sweyntooth/disclosure.html#x1-180006.8">6.8</a>
          </td>
          
          <td id="TBL-3-17-2" class="td11">
            Microchip
          </td>
          
          <td id="TBL-3-17-3" class="td11">
            ATSAMB11
          </td>
          
          <td id="TBL-3-17-4" class="td11">
            6.2
          </td>
          
          <td id="TBL-3-17-5" class="td11">
            73346
          </td>
        </tr>
        
        <tr class="hline">
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
        </tr>
        
        <tr id="TBL-3-18-">
          <td id="TBL-3-18-1" class="td11">
          </td>
        </tr>
      </table>
    </div>
  </div>
</div>

#### <span class="titlemark">2.1 </span><a id="x1-50002.1"></a>Attacks on IoT {.subsectionHead}

<div class="table row items-start justify-center">
  <div class="float">
    <div class="caption">
      <span class="id">Table 3: </span><span class="content">Products verified to be vulnerable</span>
    </div>
    
    <div class="tabular">
      <table id="TBL-4" class="tabular" cellspacing="0" cellpadding="0">
        <colgroup id="TBL-4-1g"> <col id="TBL-4-1" /> <col id="TBL-4-2" /> <col id="TBL-4-3" /> <col id="TBL-4-4" /> <col id="TBL-4-5" /></colgroup> <tr class="hline">
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
        </tr>
        
        <tr id="TBL-4-1-">
          <td id="TBL-4-1-1" class="td11">
            <div class="multicolumn">
              <span class="ptmb8t-">Product</span>
            </div>
          </td>
          
          <td id="TBL-4-1-2" class="td11">
            <span class="ptmb8t-">Category</span>
          </td>
          
          <td id="TBL-4-1-3" class="td11">
            <div class="multicolumn">
              <span class="ptmb8t-">BLE SoC</span>
            </div>
          </td>
          
          <td id="TBL-4-1-4" class="td11">
            <div class="multicolumn">
              <span class="ptmb8t-">Vulnerability</span>
            </div>
          </td>
          
          <td id="TBL-4-1-5" class="td11">
            <span class="ptmb8t-">Impact</span>
          </td>
        </tr>
        
        <tr class="hline">
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
        </tr>
        
        <tr id="TBL-4-2-">
          <td id="TBL-4-2-1" class="td11">
            <span class="ptmb8t-">Eve Energy</span>
          </td>
          
          <td id="TBL-4-2-2" class="td11">
            Smart Home
          </td>
          
          <td id="TBL-4-2-3" class="td11">
            <div class="multirow">
              DA14680
            </div>
          </td>
          
          <td id="TBL-4-2-4" class="td11">
            <div class="multicolumn">
              <div class="multirow">
                (<a href="https://asset-group.github.io/disclosures/sweyntooth/disclosure.html#x1-140006.4">6.4</a>) Silent Length Overflow
              </div>
            </div>
          </td>
          
          <td id="TBL-4-2-5" class="td11">
            <div class="multirow">
              <span id="textcolor7">Crash</span>
            </div>
          </td>
        </tr>
        
        <tr id="TBL-4-3-">
          <td id="TBL-4-3-1" class="td11">
            <span class="ptmb8t-">August Smart Lock</span>
          </td>
          
          <td id="TBL-4-3-2" class="td11">
            Smart Home
          </td>
          
          <td id="TBL-4-3-3" class="td11">
            <div class="multirow">
              DA14680
            </div>
          </td>
          
          <td id="TBL-4-3-4" class="td11">
            <div class="multicolumn">
              <div class="multirow">
                (<a href="https://asset-group.github.io/disclosures/sweyntooth/disclosure.html#x1-140006.4">6.4</a>) Silent Length Overflow
              </div>
            </div>
          </td>
          
          <td id="TBL-4-3-5" class="td11">
            <div class="multirow">
              <span id="textcolor8">Crash</span>
            </div>
          </td>
        </tr>
        
        <tr class="hline">
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
        </tr>
        
        <tr id="TBL-4-4-">
          <td id="TBL-4-4-1" class="td11">
            <div class="multirow">
              <span class="ptmb8t-">Fitbit Inspire</span>
            </div>
          </td>
          
          <td id="TBL-4-4-2" class="td11">
            <div class="multirow">
              Wearables
            </div>
          </td>
          
          <td id="TBL-4-4-3" class="td11">
            <div class="multirow">
              CY8C68237
            </div>
          </td>
          
          <td id="TBL-4-4-4" class="td11">
            <div class="multicolumn">
              (<a href="https://asset-group.github.io/disclosures/sweyntooth/disclosure.html#x1-110006.1">6.1</a>) LL Length Overflow
            </div>
          </td>
          
          <td id="TBL-4-4-5" class="td11">
            <div class="multirow">
              <span id="textcolor9">Crash</span>
            </div>
          </td>
        </tr>
        
        <tr id="TBL-4-5-">
          <td id="TBL-4-5-1" class="td11">
          </td>
          
          <td id="TBL-4-5-2" class="td11">
          </td>
          
          <td id="TBL-4-5-3" class="td11">
          </td>
          
          <td id="TBL-4-5-4" class="td11">
            <div class="multicolumn">
              (<a href="https://asset-group.github.io/disclosures/sweyntooth/disclosure.html#x1-120006.2">6.2</a>) LLID Deadlock
            </div>
          </td>
          
          <td id="TBL-4-5-5" class="td11">
            <div class="multirow">
              <span id="textcolor10">Crash</span>
            </div>
          </td>
        </tr>
        
        <tr class="hline">
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
        </tr>
        
        <tr id="TBL-4-6-">
          <td id="TBL-4-6-1" class="td11">
            <span class="ptmb8t-">CubiTag</span>
          </td>
          
          <td id="TBL-4-6-2" class="td11">
            Gadget Tracking
          </td>
          
          <td id="TBL-4-6-3" class="td11">
            CC2640R2
          </td>
          
          <td id="TBL-4-6-4" class="td11">
            <div class="multicolumn">
              (<a href="https://asset-group.github.io/disclosures/sweyntooth/disclosure.html#x1-160006.6">6.6</a>) Public Key Crash
            </div>
          </td>
          
          <td id="TBL-4-6-5" class="td11">
            <span id="textcolor11">Deadlock</span>
          </td>
        </tr>
        
        <tr class="hline">
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
        </tr>
        
        <tr id="TBL-4-7-">
          <td id="TBL-4-7-1" class="td11">
            <span class="ptmb8t-">eGeeTouch TSA Lock</span>
          </td>
          
          <td id="TBL-4-7-2" class="td11">
            Security
          </td>
          
          <td id="TBL-4-7-3" class="td11">
            CC2540
          </td>
          
          <td id="TBL-4-7-4" class="td11">
            <div class="multicolumn">
              (<a href="https://asset-group.github.io/disclosures/sweyntooth/disclosure.html#x1-150006.5">6.5</a>) Invalid Connection Request
            </div>
          </td>
          
          <td id="TBL-4-7-5" class="td11">
            <span id="textcolor12">Deadlock</span>
          </td>
        </tr>
        
        <tr class="hline">
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
          
          <td>
            <hr />
          </td>
        </tr>
        
        <tr id="TBL-4-8-">
          <td id="TBL-4-8-1" class="td11">
          </td>
        </tr>
      </table>
      
      <p>
        문제가 있는 제품들
      </p>
    </div>
  </div>
</div>

<p class="indent">
  <img src="https://asset-group.github.io/disclosures/sweyntooth/Tables/prods_affected.png" />
</p>

출처: <a href="https://asset-group.github.io/disclosures/sweyntooth/" target="_blank" rel="noopener">https://asset-group.github.io/disclosures/sweyntooth/</a>