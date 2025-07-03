# 📄 CV

<div id="pdf-viewer" style="height: 800px; overflow: auto; 
  border: 1px solid #f0f0f0; 
  border-radius: 8px; 
  margin-bottom: 12px;
  box-shadow: 0 1px 3px rgba(0,0,0,0.05);
  background-color: #fff;
"></div>

<!-- 下载按钮容器 -->
<div style="text-align: center;">
  <a href="../_pages/test.pdf" download style="
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 10px 20px;
    background: #f5f5f5;
    color: #333;
    border: 1px solid #ddd;
    border-radius: 6px;
    text-decoration: none;
    font-family: -apple-system, sans-serif;
    font-size: 14px;
    transition: all 0.2s;
  ">
    <!-- Font Awesome 下载图标（纯SVG，无需外部依赖） -->
    <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
      <path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"></path>
      <polyline points="7 10 12 15 17 10"></polyline>
      <line x1="12" y1="15" x2="12" y2="3"></line>
    </svg>
    Download PDF
  </a>
</div>

<script src="https://cdnjs.cloudflare.com/ajax/libs/pdf.js/2.12.313/pdf.min.js"></script>
<script>
  // PDF渲染逻辑（保持不变）
  pdfjsLib.GlobalWorkerOptions.workerSrc = 'https://cdnjs.cloudflare.com/ajax/libs/pdf.js/2.12.313/pdf.worker.min.js';
  pdfjsLib.getDocument('../_pages/test.pdf').promise.then(function(pdf) {
    renderPage(pdf, 1);
  }).catch(function(error) {
    document.getElementById('pdf-viewer').innerHTML = 
      '<p style="color:red; padding:20px;">PDF加载错误: 请尝试<a href="../_pages/test.pdf" download>直接下载</a></p>';
  });

  function renderPage(pdf, pageNumber) {
    pdf.getPage(pageNumber).then(function(page) {
      var viewer = document.getElementById('pdf-viewer');
      var scale = viewer.clientWidth / page.getViewport({ scale: 1.0 }).width * 0.95;
      var viewport = page.getViewport({ scale: scale });
      
      var canvas = document.createElement('canvas');
      canvas.height = viewport.height;
      canvas.width = viewport.width;
      
      viewer.innerHTML = '';
      viewer.appendChild(canvas);
      
      page.render({
        canvasContext: canvas.getContext('2d'),
        viewport: viewport
      });
    });
  }
</script>



<!--
# 📄 CV

## Zhou Jin

![Profile Picture](../../images/zj.jpg) 

**Hangzhou, China**  
**Email:** z.jin@zju.edu.cn  
**Github:** [GitHub Profile](https://github.com/dashboard)
**Google Scholar:** [Google Scholar Profile](https://scholar.google.com/citations?hl=zh-CN&user=Iw11vncAAAAJ&view_op=list_works&sortby=pubdate)
**ORCID:** [ORCID iD](https://orcid.org/0000-0002-0632-9494)

---

## Focusing on
Electronic Design Automation (EDA), VLSI CAD, Design Automation and Circuit Simulation.

---

## Current Position
**March 2025 - Present**  
Hundred-Talents Program Researcher  
Zhejiang University, School of Integrated Circuits

---

## Previous Positions
- **2023 - 2025**  
  Associate Professor, Doctoral Supervisor  
  China University of Petroleum (Beijing), School of Artificial Intelligence
- **2018 - 2022**  
  Lecturer, Master’s Supervisor  
  China University of Petroleum (Beijing), School of Information Science and Engineering
- **2016 - 2017**  
  Postdoctoral Researcher  
  Waseda University, Research Center
- **2013 - 2014**  
  GCOE Researcher  
  Waseda University, Global COE Program (21st Century Center of Excellence)

---

## Education Background
- **Ph.D. in Engineering (2012 - 2015)**  
  Waseda University, Department of Large-Scale Integrated Circuit Systems
- **M.Eng. in Engineering (2010 - 2012)**  
  Waseda University, Department of Large-Scale Integrated Circuit Systems
- **B.Sc. in Computer Science and Technology (2006 - 2010)**  
  Nanjing University, Department of Computer Science and Technology

---

## Honors and Awards
### Best Paper Awards
- SC ‘24 (CCF - A International Top - tier Conference)
  - Best Paper Award Nomination (2024)
- SC ‘23 (CCF - A International Top - tier Conference)
  - Best Paper Award
  - First recipient from Mainland China
  - Only winner at the conference (2023)
- ISEDA ‘23
  - Honorable Mention Paper Award (2023)

### Young Scientist Awards
- EDA² Open Innovation Collaboration Mechanism
  - Youth Science and Technology Award (First Edition, Sole Recipient) (2023)
- Institute of Electrical Engineers of Japan (IEE) Kyushu Branch
  - Kyushu Branch President’s Award (2013)
  

### Academic Recognition
- Beijing Association for Science and Technology
  - Selected for “Capital Frontier Academic Achievements” (2024)
  - Selected for “Youth Talent Support Program” (2022 - 2024)

  -->
