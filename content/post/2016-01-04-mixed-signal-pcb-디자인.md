---
title: Mixed-Signal PCB 디자인
author: openmicrolab
type: post
date: 2016-01-04T02:22:53+00:00
url: /mixed-signal-pcb-디자인/
categories:
  - PCB
  - Development
tags:
  - pcb

---
아날로그와 디지털이 같이 있는 회로를 PCB 디자인 할때 필요한 사항

[<img loading="lazy" class="aligncenter size-full wp-image-3477" src="/images/2016/01/www_e2v_com_content_uploads_2014_02_0999A_pdf1.png" alt="www_e2v_com_content_uploads_2014_02_0999A_pdf" width="445" height="211" srcset="/images/2016/01/www_e2v_com_content_uploads_2014_02_0999A_pdf1.png 445w, /images/2016/01/www_e2v_com_content_uploads_2014_02_0999A_pdf1-300x142.png 300w" sizes="(max-width: 445px) 100vw, 445px" />][1]

[<img loading="lazy" class="aligncenter size-full wp-image-3476" src="/images/2016/01/www_e2v_com_content_uploads_2014_02_0999A_pdf.png" alt="www_e2v_com_content_uploads_2014_02_0999A_pdf" width="507" height="229" srcset="/images/2016/01/www_e2v_com_content_uploads_2014_02_0999A_pdf.png 507w, /images/2016/01/www_e2v_com_content_uploads_2014_02_0999A_pdf-300x136.png 300w" sizes="(max-width: 507px) 100vw, 507px" />][2]

• Do not split the ground plane, use one solid plane under both analog and digital sections of the board  
• Use large area ground planes for low impedance current return paths  
• Keep over 75% board area for the ground plane  
• Separate analog and digital power planes  
• Use solid ground planes next to power planes  
• Locate all analogue components and lines over the analogue power plane and all digital components  
and lines over the digital power plane  
• Do not route traces over the split in the power planes, unless if traces that must go over the power  
plane split must be on layers adjacent to the solid ground plane  
• Think about where and how the ground return currents are actually flowing  
• Partition your PCB with separate analog and digital sections  
• Place components properly

관련자료: <a href="http://dangerousprototypes.com/2016/01/03/app-note-design-considerations-for-mixed-signal-how-to-design-a-pcb-layout/" target="_blank">http://dangerousprototypes.com/2016/01/03/app-note-design-considerations-for-mixed-signal-how-to-design-a-pcb-layout/</a>

 [1]: /images/2016/01/www_e2v_com_content_uploads_2014_02_0999A_pdf1.png
 [2]: /images/2016/01/www_e2v_com_content_uploads_2014_02_0999A_pdf.png