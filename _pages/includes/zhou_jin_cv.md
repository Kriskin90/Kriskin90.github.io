# 📄 CV

<div id="pdf-viewer" style="
  height: 800px;
  overflow: auto;
  border: 1px solid #e0e3e6;
  border-radius: 10px;
  margin-bottom: 20px;
  box-shadow: 0 5px 15px rgba(0,0,0,0.08);
  transition: all 0.4s cubic-bezier(0.22, 0.61, 0.36, 1);
  background: #fcfdff;
  position: relative;
  /* 新增装饰性边框 */
  padding: 2px;
  background-clip: padding-box;
">
  <!-- 装饰性边框 -->
  <div style="
    position: absolute;
    top: -3px;
    left: -3px;
    right: -3px;
    bottom: -3px;
    border: 2px solid rgba(168, 187, 206, 0.3);
    border-radius: 12px;
    pointer-events: none;
    z-index: -1;
  "></div>
</div>

<!-- 下载按钮容器 -->
<div style="text-align: center; margin-top: 12px;">
  <a href="../_pages/test.pdf" download style="
    display: inline-flex;
    align-items: center;
    gap: 7px;
    padding: 10px 20px;
    background: linear-gradient(to bottom, #f8f9fa, #f1f3f5);
    color: #2c3e50;
    border: 1px solid #d6d9dc;
    border-radius: 6px;
    text-decoration: none;
    font-family: 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
    font-size: 14px;
    font-weight: 500;
    letter-spacing: 0.4px;
    transition: all 0.3s ease-out;
    box-shadow: 0 2px 4px rgba(0,0,0,0.05);
    position: relative;
    overflow: hidden;
  ">
    <!-- 按钮悬停效果 -->
    <span style="
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: linear-gradient(to right, rgba(255,255,255,0.1), rgba(255,255,255,0.3));
      transform: translateX(-100%);
      transition: transform 0.3s ease;
    "></span>
    <!-- 优化后的下载图标 -->
    <svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.4" stroke-linecap="round" style="flex-shrink: 0;">
      <path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"></path>
      <polyline points="7 10 12 15 17 10" stroke-linejoin="round"></polyline>
      <line x1="12" y1="15" x2="12" y2="3"></line>
    </svg>
    Download PDF
  </a>
</div>

<script src="https://cdnjs.cloudflare.com/ajax/libs/pdf.js/2.12.313/pdf.min.js"></script>
<script>
  // PDF渲染逻辑
  pdfjsLib.GlobalWorkerOptions.workerSrc = 'https://cdnjs.cloudflare.com/ajax/libs/pdf.js/2.12.313/pdf.worker.min.js';
  pdfjsLib.getDocument('../_pages/test.pdf').promise.then(function(pdf) {
    renderPage(pdf, 1);
  }).catch(function(error) {
    document.getElementById('pdf-viewer').innerHTML = 
      '<div style="color:#e74c3c; padding:24px; font-size:14px; text-align:center; background:#fff9f9; border-radius:6px; margin:12px; border:1px solid #ffebee;">PDF加载错误: 请尝试<a href="../_pages/test.pdf" download style="color:#3498db; text-decoration:none; font-weight:600; border-bottom:1px dashed #3498db;">直接下载</a></div>';
  });

  function renderPage(pdf, pageNumber) {
    pdf.getPage(pageNumber).then(function(page) {
      var viewer = document.getElementById('pdf-viewer');
      var scale = viewer.clientWidth / page.getViewport({ scale: 1.0 }).width * 0.93;
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
      
      // 加载完成后的精致动画
      viewer.style.boxShadow = '0 8px 20px rgba(0,0,0,0.1)';
      viewer.style.borderColor = '#d0dce8';
      viewer.querySelector('div').style.borderColor = 'rgba(168, 187, 206, 0.5)';
    });
  }
  
  // 为下载按钮添加悬停效果
  document.querySelector('a[download]').addEventListener('mouseenter', function() {
    this.querySelector('span').style.transform = 'translateX(0)';
    this.style.boxShadow = '0 3px 8px rgba(0,0,0,0.1)';
  });
  document.querySelector('a[download]').addEventListener('mouseleave', function() {
    this.querySelector('span').style.transform = 'translateX(-100%)';
    this.style.boxShadow = '0 2px 4px rgba(0,0,0,0.05)';
  });
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
