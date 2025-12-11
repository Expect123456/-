<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>马家窑食养</title>
    <script src="app.js"></script>
    <script src="web-framework.js"></script>
    <script src="pages/index/index.js"></script>
    <script src="pages/recipe/recipe.js"></script>
    <script src="pages/customize/customize.js"></script>
    <script src="pages/data/data.js"></script>
    <script>
        // 全局变量，用于跟踪是否有点击交互
        let hasClickInteraction = false;
        
        // 页面切换逻辑
        function switchPage(pageName) {
            // 隐藏所有页面
            document.querySelectorAll('[id$="-page"]').forEach(page => {
                page.style.display = 'none';
            });
            
            // 显示目标页面
            const targetPage = document.getElementById(pageName);
            if (targetPage) {
                targetPage.style.display = 'block';
            }
        }
        
        // 页面加载完成后初始化
        document.addEventListener('DOMContentLoaded', function() {
            // 给功能项添加点击事件
            document.querySelectorAll('.feature-item').forEach(item => {
                item.addEventListener('click', function() {
                    const page = this.getAttribute('data-page');
                    if (page) {
                        switchPage(page);
                        hasClickInteraction = true;
                    }
                });
            });
            
            // 给底部导航按钮添加点击事件
            document.querySelectorAll('.nav-button').forEach(button => {
                button.addEventListener('click', function() {
                    const page = this.getAttribute('data-page');
                    if (page) {
                        switchPage(page);
                        hasClickInteraction = true;
                    }
                });
            });
            
            // 给所有可点击元素添加点击事件，标记有点击交互
            document.querySelectorAll('button, .feature-item, .recipe-item, .option-item, .pattern-item, .tab-item, .back-button, .filter-btn').forEach(element => {
                element.addEventListener('click', function() {
                    hasClickInteraction = true;
                });
            });
            
            // 添加全局滚动事件监听器
            document.addEventListener('scroll', function(e) {
                // 确保在滚动时不会显示健康目标模态框
                document.getElementById('health-goal-modal').style.display = 'none';
                
                // 如果没有点击交互，阻止某些可能的自动触发行为
                if (!hasClickInteraction) {
                    // 这里可以根据需要添加更多的限制逻辑
                    console.log('禁止在无点击交互情况下的滚动触发行为');
                }
            });
            
            // 添加触摸滚动事件监听器
            document.addEventListener('touchmove', function(e) {
                // 确保在触摸滚动时不会显示健康目标模态框
                document.getElementById('health-goal-modal').style.display = 'none';
                
                // 如果没有点击交互，阻止某些可能的自动触发行为
                if (!hasClickInteraction) {
                    console.log('禁止在无点击交互情况下的触摸滚动触发行为');
                }
            }, { passive: false });
        });
    </script>
    <style>
        /* 全局样式 */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
            background-image: url('images/背景1.jpg');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            color: #333;
            line-height: 1.6;
            /* 禁止页面滚动 */
            overflow: hidden;
            height: 100vh;
        }
        
        /* 容器样式 */
        .container {
            max-width: 100%;
            min-height: 100vh;
            background-color: rgba(255, 255, 255, 0.85);
            padding: 20px;
        }
        
        /* 主页面样式 */
        #index-page {
            background-color: transparent;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            height: 100vh;
            /* 允许垂直滚动显示全部内容 */
            overflow-y: auto;
        }
        
        .header {
            text-align: center;
            padding: 20px 0;
            background-color: rgba(255, 255, 255, 0.9);
            border-radius: 10px;
            margin-bottom: 20px;
        }
        
        .header-title {
            font-size: 36px;
            color: #D4AF37;
            font-weight: bold;
            margin-bottom: 10px;
        }
        
        .header-subtitle {
            font-size: 18px;
            color: #666;
        }
        
        .scan-button {
            background-color: #D4AF37;
            color: white;
            border: none;
            padding: 15px 30px;
            font-size: 18px;
            border-radius: 50px;
            cursor: pointer;
            margin: 20px auto;
            display: block;
            transition: all 0.3s;
        }
        
        .scan-button:hover {
            background-color: #C59E2E;
            transform: scale(1.05);
        }
        
        .core-features {
            display: flex;
            flex-direction: column;
            gap: 15px;
            margin-bottom: 30px;
        }
        
        .feature-item {
            display: flex;
            align-items: center;
            background-color: rgba(255, 255, 255, 0.9);
            padding: 15px;
            border-radius: 10px;
            cursor: pointer;
            transition: all 0.3s;
        }
        
        .feature-item:hover {
            background-color: rgba(255, 249, 230, 0.9);
            transform: translateX(5px);
        }
        
        .feature-icon {
            font-size: 32px;
            margin-right: 15px;
        }
        
        .feature-text {
            font-size: 18px;
            font-weight: bold;
        }
        
        /* 食谱页面样式 */
        #recipe-page {
            display: none;
            height: 100vh;
            overflow-y: auto;
        }
        
        #data-page {
            display: none;
            height: 100vh;
            overflow-y: auto;
        }
        
        #customize-page {
            display: none;
            height: 100vh;
            overflow-y: auto;
        }
        
        .page-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 10px 0;
            margin-bottom: 20px;
            border-bottom: 1px solid #eee;
        }
        
        .page-title {
            font-size: 24px;
            font-weight: bold;
            color: #D4AF37;
        }
        
        .back-button {
            background-color: #D4AF37;
            color: white;
            border: none;
            padding: 8px 15px;
            border-radius: 5px;
            cursor: pointer;
            transition: all 0.3s;
        }
        
        .back-button:hover {
            background-color: #C59E2E;
        }
        
        .recipe-filters {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin-bottom: 20px;
        }
        
        .filter-btn {
            background-color: #fff;
            border: 2px solid #ddd;
            padding: 8px 15px;
            border-radius: 20px;
            cursor: pointer;
            transition: all 0.3s;
        }
        
        .filter-btn.active {
            border-color: #D4AF37;
            background-color: #FFF9E6;
            color: #D4AF37;
        }
        
        .recipe-list {
            display: flex;
            flex-direction: column;
            gap: 20px;
        }
        
        /* 食谱卡片 */
        .recipe-card {
            background-color: #ffffff;
            border-radius: 16px;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.08);
            overflow: hidden;
            transition: all 0.3s ease;
            border: 2px solid transparent;
            display: flex;
            flex-direction: column;
            height: 100%;
        }
        
        .recipe-card:hover {
            transform: translateY(-4px);
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.12);
            border-color: #D4AF37;
        }
        
        /* 食谱图片区域 */
        .recipe-image {
            position: relative;
            width: 100%;
            height: 200px;
            background: linear-gradient(135deg, #F5F7FA 0%, #C3CFE2 100%);
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .recipe-placeholder {
            font-size: 50px;
            font-weight: 600;
            color: #D4AF37;
            opacity: 0.8;
            text-align: center;
            padding: 10px;
            line-height: 0.9;
            word-break: break-word;
            overflow: hidden;
            letter-spacing: 5px;
        }
        
        /* 食谱类型徽章 */
        .recipe-type-badge {
            position: absolute;
            top: 12px;
            left: 12px;
            font-size: 16px;
            font-weight: 500;
            color: #ffffff;
            background-color: #D4AF37;
            padding: 6px 14px;
            border-radius: 20px;
            z-index: 1;
        }
        
        /* 甘肃专属标识 */
        .gansu-special {
            position: absolute;
            top: 12px;
            right: 12px;
            font-size: 24px;
            z-index: 1;
            background: linear-gradient(135deg, #D4AF37 0%, #FFD700 100%);
            border-radius: 50%;
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 4px 10px rgba(212, 175, 55, 0.3);
            animation: pulse 2s infinite;
        }
        
        @keyframes pulse {
            0% { box-shadow: 0 4px 10px rgba(212, 175, 55, 0.3); }
            50% { box-shadow: 0 6px 15px rgba(212, 175, 55, 0.6); }
            100% { box-shadow: 0 4px 10px rgba(212, 175, 55, 0.3); }
        }
        
        /* 食谱内容区域 */
        .recipe-content {
            padding: 20px;
            flex: 1;
            display: flex;
            flex-direction: column;
        }
        
        .recipe-title {
            font-size: 24px;
            font-weight: 600;
            color: #333333;
            margin-bottom: 12px;
            line-height: 1.4;
            overflow: hidden;
            text-overflow: ellipsis;
            display: -webkit-box;
            -webkit-line-clamp: 2;
            -webkit-box-orient: vertical;
        }
        
        /* 食谱元信息 */
        .recipe-meta {
            display: flex;
            gap: 20px;
            margin-bottom: 20px;
        }
        
        .meta-item {
            font-size: 14px;
            color: #666666;
            display: flex;
            align-items: center;
            gap: 5px;
        }
        
        /* 营养信息 */
        .nutrition-info {
            display: flex;
            justify-content: space-around;
            margin-bottom: 16px;
            padding: 12px;
            background-color: #f8f9fa;
            border-radius: 12px;
        }
        
        .nutrition-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 4px;
        }
        
        .nutrition-label {
            font-size: 14px;
            color: #999999;
        }
        
        .nutrition-value {
            font-size: 16px;
            color: #333333;
            font-weight: 500;
        }
        
        /* 食谱标签 */
        .recipe-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin-top: auto;
        }
        
        .tag {
            font-size: 12px;
            padding: 4px 10px;
            border-radius: 12px;
            font-weight: 500;
        }
        
        .calorie-tag {
            background-color: #FFF3E0;
            color: #F57C00;
        }
        
        .protein-tag {
            background-color: #E3F2FD;
            color: #1976D2;
        }
        
        /* Modal Styles */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-color: rgba(0, 0, 0, 0.6);
            z-index: 1000;
            display: none;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }
        
        .modal-container {
            width: 100%;
            max-width: 800px;
            max-height: 85vh;
            background-color: white;
            border-radius: 24px;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.25);
            overflow: hidden;
            display: flex;
            flex-direction: column;
        }
        
        /* Modal Header */
        .modal-header {
            padding: 24px 32px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background-color: #fff;
            border-bottom: 1px solid #f0f0f0;
            position: sticky;
            top: 0;
            z-index: 10;
        }
        
        .modal-title {
            font-size: 28px;
            font-weight: 600;
            color: #333333;
            flex: 1;
            overflow: hidden;
            text-overflow: ellipsis;
            white-space: nowrap;
            margin-right: 20px;
        }
        
        .close-btn {
            width: 60px;
            height: 60px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
            background-color: #f5f5f5;
            border: none;
            cursor: pointer;
            font-size: 36px;
            color: #666666;
            transition: all 0.3s ease;
        }
        
        .close-btn:hover {
            background-color: #e8e8e8;
            color: #333333;
            transform: scale(0.95);
        }
        
        /* Modal Body */
        .modal-body {
            padding: 32px;
            overflow-y: auto;
            flex: 1;
        }
        
        /* Modal Content Sections */
        .modal-section {
            margin-bottom: 32px;
        }
        
        .section-title {
            font-size: 20px;
            font-weight: 600;
            color: #333333;
            margin-bottom: 16px;
            padding-bottom: 8px;
            border-bottom: 2px solid #D4AF37;
        }
        
        /* Ingredients Grid */
        .ingredients-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 16px;
        }
        
        .ingredient-item {
            background-color: #f8f9fa;
            padding: 16px;
            border-radius: 12px;
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
        }
        
        .ingredient-name {
            font-size: 14px;
            color: #333333;
            font-weight: 500;
            margin-bottom: 8px;
        }
        
        .ingredient-amount {
            font-size: 14px;
            color: #666666;
        }
        
        /* Steps Container */
        .steps-container {
            display: flex;
            flex-direction: column;
            gap: 24px;
        }
        
        .step-item {
            display: flex;
            gap: 16px;
        }
        
        .step-number {
            width: 40px;
            height: 40px;
            background-color: #D4AF37;
            color: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 600;
            flex-shrink: 0;
        }
        
        .step-content {
            flex: 1;
            background-color: #f8f9fa;
            padding: 16px;
            border-radius: 12px;
            font-size: 14px;
            line-height: 1.6;
            color: #333333;
        }
        
        /* Recipe Description */
        .recipe-description {
            font-size: 16px;
            line-height: 1.8;
            color: #666666;
            background-color: #f8f9fa;
            padding: 20px;
            border-radius: 12px;
        }
        
        /* Modal Image */
        .modal-image {
            position: relative;
            width: 100%;
            height: 240px;
            background: linear-gradient(135deg, #F5F7FA 0%, #C3CFE2 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 16px;
            margin-bottom: 24px;
        }
        
        /* Recipe Modal Placeholder */
        #recipe-modal-placeholder {
            font-size: 50px;
            font-weight: 600;
            color: #D4AF37;
            opacity: 0.8;
            text-align: center;
            padding: 10px;
            line-height: 0.9;
            word-break: break-word;
            overflow: hidden;
            letter-spacing: 5px;
        }
        
        /* Info Cards */
        .info-card {
            background-color: #ffffff;
            border-radius: 16px;
            padding: 24px;
            margin-bottom: 24px;
            box-shadow: 0 2px 12px rgba(0, 0, 0, 0.08);
            border: 1px solid #f0f0f0;
        }
        
        /* Basic Info Grid */
        .basic-info-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 16px;
        }
        
        .basic-info-item {
            display: flex;
            align-items: center;
            gap: 12px;
        }
        
        .info-icon {
            font-size: 24px;
            width: 40px;
            height: 40px;
            background-color: #f8f9fa;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .info-content {
            flex: 1;
        }
        
        .info-label {
            font-size: 14px;
            color: #999999;
            margin-bottom: 4px;
        }
        
        .info-value {
            font-size: 16px;
            color: #333333;
            font-weight: 500;
        }
        
        /* Nutrition Grid */
        .nutrition-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 16px;
        }
        
        .nutrition-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
            padding: 16px;
            background-color: #f8f9fa;
            border-radius: 12px;
        }
        
        .nutrition-icon {
            font-size: 24px;
            margin-bottom: 8px;
        }
        
        .nutrition-label {
            font-size: 12px;
            color: #999999;
            margin-bottom: 4px;
        }
        
        .nutrition-value {
            font-size: 16px;
            color: #333333;
            font-weight: 600;
        }
        
        /* Footer Actions */
        .footer-actions {
            display: flex;
            gap: 12px;
            justify-content: center;
            flex-wrap: wrap;
            margin-top: 32px;
            padding-top: 24px;
            border-top: 1px solid #f0f0f0;
        }
        
        .footer-btn {
            flex: 1;
            min-width: 120px;
            padding: 16px 24px;
            font-size: 16px;
            font-weight: 500;
            color: #333333;
            background-color: #f8f9fa;
            border: none;
            border-radius: 12px;
            cursor: pointer;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
        }
        
        .footer-btn:hover {
            background-color: #D4AF37;
            color: white;
            transform: translateY(-2px);
            box-shadow: 0 4px 12px rgba(212, 175, 55, 0.3);
        }
        
        /* Gansu Special Badge */
        .gansu-special-badge {
            font-size: 24px;
            background: linear-gradient(135deg, #D4AF37 0%, #FFD700 100%);
            border-radius: 50%;
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 4px 10px rgba(212, 175, 55, 0.3);
        }
        
        .gansu-special-text {
            font-size: 14px;
            color: #D4AF37;
            font-weight: 700;
            background: linear-gradient(135deg, rgba(212, 175, 55, 0.1) 0%, rgba(255, 215, 0, 0.1) 100%);
            padding: 4px 10px;
            border-radius: 12px;
            border: 1px solid #D4AF37;
            margin-top: 5px;
        }
        
        /* 定制页面样式 */
        #customize-page {
            display: none;
        }
        
        .progress-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin: 20px 0;
            padding: 0 10px;
        }
        
        .progress-step {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background-color: #ddd;
            color: #fff;
            display: flex;
            justify-content: center;
            align-items: center;
            font-weight: bold;
            transition: all 0.3s;
        }
        
        .progress-step.active {
            background-color: #D4AF37;
        }
        
        .progress-line {
            flex: 1;
            height: 4px;
            background-color: #ddd;
            transition: all 0.3s;
        }
        
        .progress-line.active {
            background-color: #D4AF37;
        }
        
        .progress-labels {
            display: flex;
            justify-content: space-between;
            padding: 0 5px;
            margin-bottom: 20px;
        }
        
        .progress-label {
            font-size: 14px;
            color: #999;
            text-align: center;
            width: 80px;
            transition: all 0.3s;
        }
        
        .progress-label.active {
            color: #D4AF37;
            font-weight: bold;
        }
        
        .step-content {
            background-color: #fff;
            border-radius: 10px;
            padding: 20px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            margin-bottom: 20px;
        }
        
        .step-title {
            font-size: 24px;
            font-weight: bold;
            text-align: center;
            margin-bottom: 10px;
            color: #333;
        }
        
        .step-description {
            font-size: 16px;
            text-align: center;
            color: #666;
            margin-bottom: 30px;
        }
        
        .options-container {
            margin-bottom: 30px;
        }
        
        .option-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px;
            border: 2px solid #ddd;
            border-radius: 10px;
            margin-bottom: 15px;
            cursor: pointer;
            transition: all 0.3s;
        }
        
        .option-item:hover,
        .option-item.selected {
            border-color: #D4AF37;
            background-color: #FFF9E6;
        }
        
        .option-text {
            font-size: 18px;
            color: #333;
        }
        
        .option-check {
            font-size: 20px;
            color: #D4AF37;
            font-weight: bold;
        }
        
        .patterns-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            margin-bottom: 30px;
        }
        
        .pattern-item {
            width: calc(50% - 10px);
            padding: 20px;
            border: 2px solid #ddd;
            border-radius: 10px;
            margin-bottom: 15px;
            display: flex;
            flex-direction: column;
            align-items: center;
            position: relative;
            cursor: pointer;
            transition: all 0.3s;
        }
        
        .pattern-item:hover,
        .pattern-item.selected {
            border-color: #D4AF37;
            background-color: #FFF9E6;
        }
        
        .pattern-icon {
            font-size: 48px;
            margin-bottom: 10px;
        }
        
        .pattern-name {
            font-size: 16px;
            color: #333;
            text-align: center;
        }
        
        .pattern-check {
            position: absolute;
            top: 10px;
            right: 10px;
            font-size: 20px;
            color: #D4AF37;
            font-weight: bold;
        }
        
        .button-group {
            display: flex;
            justify-content: space-between;
            gap: 10px;
        }
        
        .btn {
            flex: 1;
            padding: 12px;
            border: none;
            border-radius: 5px;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s;
        }
        
        .btn-primary {
            background-color: #D4AF37;
            color: white;
        }
        
        .btn-primary:hover {
            background-color: #C59E2E;
        }
        
        .btn-secondary {
            background-color: #ddd;
            color: #333;
        }
        
        .btn-secondary:hover {
            background-color: #ccc;
        }
        
        .btn-success {
            background-color: #3CC51F;
            color: white;
        }
        
        .btn-success:hover {
            background-color: #36B319;
        }
        
        /* 模态框样式 */
        .modal {
            display: none;
            position: fixed;
            z-index: 1000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
        }
        
        .modal-content {
            background-color: white;
            margin: 10% auto;
            padding: 20px;
            border-radius: 10px;
            width: 90%;
            max-width: 500px;
            max-height: 80vh;
            overflow-y: auto;
        }
        
        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }
        
        .modal-title {
            font-size: 24px;
            font-weight: bold;
            color: #D4AF37;
        }
        
        .close-btn {
            font-size: 28px;
            font-weight: bold;
            cursor: pointer;
            color: #aaa;
        }
        
        .close-btn:hover {
            color: #333;
        }
        
        .modal-body {
            margin-bottom: 20px;
        }
        
        .recipe-actions {
            margin-top: 20px;
            display: flex;
            gap: 10px;
            justify-content: center;
        }
        
        .action-btn {
            padding: 8px 16px;
            border: none;
            border-radius: 4px;
            background-color: #4CAF50;
            color: white;
            font-size: 14px;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        
        .action-btn:hover {
            background-color: #45a049;
        }
        
        .recipe-actions .action-btn:nth-child(2) {
            background-color: #008CBA;
        }
        
        .recipe-actions .action-btn:nth-child(2):hover {
            background-color: #007B9E;
        }
        
        .recipe-detail-info {
            margin-bottom: 20px;
        }
        
        .info-row {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
            padding-bottom: 10px;
            border-bottom: 1px solid #eee;
        }
        
        .info-label {
            font-weight: bold;
            color: #666;
        }
        
        .info-value {
            color: #333;
        }
        
        /* 数据页面样式 */
        #data-page {
            display: none;
        }
        
        /* 标签页样式 */
        .tab-container {
            display: flex;
            margin-bottom: 20px;
            border-bottom: 1px solid #eee;
        }
        
        .tab-item {
            flex: 1;
            text-align: center;
            padding: 15px 0;
            cursor: pointer;
            font-size: 16px;
            color: #666;
            transition: all 0.3s;
            border-bottom: 2px solid transparent;
        }
        
        .tab-item.active {
            color: #D4AF37;
            border-bottom-color: #D4AF37;
            font-weight: bold;
        }
        
        /* 标签内容样式 */
        .tab-content {
            display: none;
        }
        
        .tab-content.active {
            display: block;
        }
        
        /* 卡片样式 */
        .card {
            background-color: #fff;
            border-radius: 10px;
            padding: 20px;
            margin-bottom: 20px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }
        
        .subtitle {
            font-size: 18px;
            font-weight: bold;
            margin-bottom: 20px;
            color: #333;
        }
        
        /* 表单样式 */
        .form-item {
            margin-bottom: 20px;
        }
        
        .form-label {
            display: block;
            margin-bottom: 8px;
            font-size: 16px;
            color: #666;
            font-weight: bold;
        }
        
        .picker, .input {
            width: 100%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 16px;
        }
        
        .form-button {
            text-align: center;
            margin-top: 30px;
        }
        
        /* 适配建议样式 */
        .adaptation-info {
            display: flex;
            gap: 20px;
        }
        
        .info-card {
            flex: 1;
            background-color: #f8f8f8;
            padding: 20px;
            border-radius: 10px;
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .info-icon {
            font-size: 32px;
        }
        
        .info-content {
            flex: 1;
        }
        
        .info-title {
            font-size: 14px;
            color: #666;
            margin-bottom: 5px;
        }
        
        .info-value {
            font-size: 24px;
            font-weight: bold;
            color: #333;
        }
        
        /* 图表样式 */
        .chart-container {
            margin-bottom: 20px;
        }
        
        .chart {
            width: 100%;
            height: 200px;
        }
        
        .chart-info {
            display: flex;
            justify-content: space-around;
            margin-top: 20px;
        }
        
        .chart-stat {
            text-align: center;
        }
        
        .stat-label {
            font-size: 14px;
            color: #666;
            margin-bottom: 5px;
        }
        
        .stat-value {
            font-size: 24px;
            font-weight: bold;
        }
        
        .color-health {
            color: #3CC51F;
        }
        
        /* 统计网格样式 */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 20px;
        }
        
        .stat-item {
            text-align: center;
            background-color: #f8f8f8;
            padding: 20px;
            border-radius: 10px;
        }
        
        .stat-number {
            font-size: 32px;
            font-weight: bold;
            color: #D4AF37;
            margin-bottom: 5px;
        }
        
        .stat-desc {
            font-size: 14px;
            color: #666;
        }
        
        /* 权益列表样式 */
        .rewards-list {
            display: flex;
            flex-direction: column;
            gap: 20px;
        }
        
        .reward-item {
            cursor: pointer;
            transition: all 0.3s;
        }
        
        .reward-item:hover {
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.15);
        }
        
        .reward-header {
            display: flex;
            align-items: center;
            gap: 15px;
            margin-bottom: 10px;
        }
        
        .reward-icon {
            font-size: 32px;
        }
        
        .reward-title {
            font-size: 18px;
            font-weight: bold;
            color: #333;
        }
        
        .reward-description {
            font-size: 14px;
            color: #666;
            margin-bottom: 10px;
            line-height: 1.5;
        }
        
        .reward-requirement {
            margin-bottom: 10px;
            font-size: 14px;
        }
        
        .requirement-label {
            font-weight: bold;
            color: #666;
        }
        
        .requirement-value {
            color: #999;
        }
        
        .reward-status {
            text-align: right;
        }
        
        .status-badge {
            display: inline-block;
            padding: 5px 15px;
            background-color: #3CC51F;
            color: white;
            border-radius: 15px;
            font-size: 12px;
        }
        
        /* 提示样式 */
        .tips {
            background-color: #FFF9E6;
            padding: 15px;
            border-radius: 10px;
            display: flex;
            align-items: center;
            gap: 10px;
            margin-top: 20px;
        }
        
        .tips-icon {
            font-size: 20px;
        }
        
        .tips-text {
            flex: 1;
            font-size: 14px;
            color: #D4AF37;
        }
        
        /* 权益弹窗样式 */
        .reward-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            display: none;
            z-index: 1000;
        }
        
        .reward-popup {
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background-color: white;
            border-radius: 10px;
            width: 90%;
            max-width: 400px;
            z-index: 1001;
            display: none;
        }
        
        .popup-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px;
            border-bottom: 1px solid #eee;
        }
        
        .popup-title {
            font-size: 20px;
            font-weight: bold;
            color: #333;
        }
        
        .popup-close {
            font-size: 24px;
            cursor: pointer;
            color: #999;
            transition: all 0.3s;
        }
        
        .popup-close:hover {
            color: #333;
        }
        
        .popup-content {
            padding: 20px;
        }
        
        .reward-image {
            width: 100%;
            height: 200px;
            border-radius: 5px;
            overflow: hidden;
            margin-bottom: 20px;
        }
        
        .reward-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .info-item {
            margin-bottom: 15px;
            font-size: 14px;
        }
        
        .info-label {
            font-weight: bold;
            color: #666;
            margin-right: 5px;
        }
        
        .redeem-code {
            font-weight: bold;
            color: #D4AF37;
            font-size: 18px;
            letter-spacing: 2px;
        }
        
        .popup-footer {
            padding: 20px;
            border-top: 1px solid #eee;
            text-align: center;
        }
        
        /* 按钮样式 */
        .btn {
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            font-size: 16px;
            cursor: pointer;
            transition: all 0.3s;
            margin: 0 5px;
        }
        
        .btn-primary {
            background-color: #D4AF37;
            color: white;
        }
        
        .btn-primary:hover {
            background-color: #C59E2E;
        }
        
        .btn-secondary {
            background-color: #eee;
            color: #333;
        }
        
        .btn-secondary:hover {
            background-color: #ddd;
        }
        
        .ingredients-list,
        .steps-list {
            margin-bottom: 20px;
        }
        
        .list-title {
            font-size: 18px;
            font-weight: bold;
            margin-bottom: 10px;
            color: #D4AF37;
        }
        
        .ingredients-list ul,
        .steps-list ol {
            padding-left: 20px;
        }
        
        .ingredients-list li,
        .steps-list li {
            margin-bottom: 8px;
            color: #333;
        }
        
        /* 预览容器 */
        .preview-container {
            margin-bottom: 30px;
        }
        
        .preview-image {
            width: 100%;
            height: 250px;
            border-radius: 10px;
            overflow: hidden;
            margin-bottom: 20px;
        }
        
        .preview-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .preview-info {
            text-align: center;
        }
        
        .preview-title {
            font-size: 20px;
            font-weight: bold;
            color: #333;
            margin-bottom: 5px;
        }
        
        .preview-pattern {
            font-size: 32px;
            color: #D4AF37;
            font-weight: bold;
            margin-bottom: 15px;
        }
        
        .preview-description {
            text-align: left;
        }
        
        .preview-item {
            font-size: 16px;
            color: #666;
            margin-bottom: 8px;
        }
    </style>
</head>
<body>
    <!-- 主页面 -->
    <div id="index-page" class="container">
        <div class="header">
            <div class="header-title">马家窑食养</div>
            <div class="header-subtitle">传承千年文化，守护现代健康</div>
        </div>
        
        <button class="scan-button" onclick="scanCode()">📱 扫码绑定餐具</button>
        
        <div class="core-features">
            <div class="feature-item" onclick="goToRecipePage()">
                <span class="feature-icon">🍲</span>
                <span class="feature-text">膳食匹配</span>
            </div>
            <div class="feature-item" onclick="goToDataPage()">
                <span class="feature-icon">📊</span>
                <span class="feature-text">健康数据</span>
            </div>
            <div class="feature-item" onclick="goToCustomizePage()">
                <span class="feature-icon">🎨</span>
                <span class="feature-text">专属纹样定制</span>
            </div>
            <div class="feature-item" onclick="showHealthGoalModal(event)">
                <span class="feature-icon">🎯</span>
                <span class="feature-text">健康目标设定</span>
            </div>
        </div>
    </div>
    
    <!-- 食谱页面 -->
    <div id="recipe-page" class="container">
        <div class="page-header">
            <button class="back-button" onclick="goBack('index')">返回</button>
            <div class="page-title">膳食匹配</div>
        </div>
        
        <div class="recipe-filters">
            <button class="filter-btn active" data-filter="all" onclick="filterRecipes(this)">全部</button>
            <button class="filter-btn" data-filter="减脂" onclick="filterRecipes(this)">减脂</button>
            <button class="filter-btn" data-filter="控糖" onclick="filterRecipes(this)">控糖</button>
            <button class="filter-btn" data-filter="控盐" onclick="filterRecipes(this)">控盐</button>
            <button class="filter-btn" data-filter="增肌" onclick="filterRecipes(this)">增肌</button>
            <button class="filter-btn" data-filter="均衡饮食" onclick="filterRecipes(this)">均衡饮食</button>
            <button class="filter-btn" data-filter="clear" onclick="clearFilter()">清除</button>
        </div>
        
        <div id="recipe-list" class="recipe-list">
            <!-- 食谱列表将通过JavaScript动态生成 -->
        </div>
    </div>
    
    <!-- 定制页面 -->
    <div id="customize-page" class="container">
        <div class="page-header">
            <button class="back-button" onclick="goBack('index')">返回</button>
            <div class="page-title">专属纹样定制</div>
        </div>
        
        <div class="progress-container">
            <div class="progress-step active" id="step-1">1</div>
            <div class="progress-line" id="line-1"></div>
            <div class="progress-step" id="step-2">2</div>
            <div class="progress-line" id="line-2"></div>
            <div class="progress-step" id="step-3">3</div>
            <div class="progress-line" id="line-3"></div>
            <div class="progress-step" id="step-4">4</div>
        </div>
        
        <div class="progress-labels">
            <div class="progress-label active">绑定餐具</div>
            <div class="progress-label">健康目标</div>
            <div class="progress-label">选择纹样</div>
            <div class="progress-label">生成预览</div>
        </div>
        
        <!-- 步骤1: 绑定餐具 -->
        <div class="step-content" id="step-content-1">
            <div class="step-title">绑定您的餐具</div>
            <div class="step-description">请扫描餐具上的二维码进行绑定</div>
            <div class="scan-area">
                <div class="scan-icon">📱</div>
                <div class="scan-text">扫描二维码</div>
            </div>
            <button class="btn btn-primary" onclick="scanCodeAndNext()">扫码绑定</button>
        </div>
        
        <!-- 步骤2: 选择健康目标 -->
        <div class="step-content" id="step-content-2" style="display: none;">
            <div class="step-title">选择您的健康目标</div>
            <div class="step-description">根据您的需求，我们将为您匹配最适合的纹样</div>
            <div class="options-container" id="health-goals-container">
                <!-- 健康目标选项将通过JavaScript动态生成 -->
            </div>
            <div class="button-group">
                <button class="btn btn-secondary" onclick="prevStep()">上一步</button>
                <button class="btn btn-primary" onclick="nextStep()">下一步</button>
            </div>
        </div>
        
        <!-- 步骤3: 选择马家窑纹样 -->
        <div class="step-content" id="step-content-3" style="display: none;">
            <div class="step-title">选择马家窑基础纹样</div>
            <div class="step-description">选择您喜爱的马家窑传统纹样</div>
            <div class="patterns-container" id="patterns-container">
                <!-- 纹样选项将通过JavaScript动态生成 -->
            </div>
            <div class="button-group">
                <button class="btn btn-secondary" onclick="prevStep()">上一步</button>
                <button class="btn btn-primary" onclick="nextStep()">生成纹样</button>
            </div>
        </div>
        
        <!-- 步骤4: 生成预览 -->
        <div class="step-content" id="step-content-4" style="display: none;">
            <div class="step-title">您的专属纹样已生成</div>
            <div class="step-description">根据您的健康目标和选择的纹样，为您定制专属组合</div>
            
            <div class="preview-container">
                <div class="preview-image">
                    <img id="custom-pattern-image" src="" alt="专属纹样">
                </div>
                <div class="preview-info">
                    <div class="preview-title">专属组合纹</div>
                    <div class="preview-pattern" id="custom-pattern"></div>
                    <div class="preview-description">
                        <div class="preview-item">健康目标：<span id="selected-goal-text"></span></div>
                        <div class="preview-item">基础纹样：<span id="selected-pattern-text"></span></div>
                    </div>
                </div>
            </div>
            
            <div class="button-group">
                <button class="btn btn-secondary" onclick="restartCustomize()">重新定制</button>
                <button class="btn btn-primary" onclick="matchRecipes()">匹配食谱</button>
                <button class="btn btn-success" onclick="completeCustomize()">完成</button>
            </div>
        </div>
    </div>
    
    <!-- 食谱详情模态框 -->
    <div id="recipe-modal" class="modal-overlay">
        <div class="modal-container">
            <div class="modal-header">
                <div class="modal-title" id="recipe-modal-title">食谱详情</div>
                <span class="close-btn" onclick="closeRecipeModal()">&times;</span>
            </div>
            <div class="modal-body">
                <!-- 食谱图片区域 -->
                <div class="modal-image">
                    <div id="recipe-modal-placeholder"></div>
                    <div class="recipe-type-badge" id="recipe-modal-type"></div>
                    <div id="recipe-modal-gansu" style="display: none;">
                        <div class="gansu-special-badge">🍜</div>
                        <div class="gansu-special-text">甘肃特色</div>
                    </div>
                </div>
                
                <!-- 基础信息卡片 -->
                <div class="info-card basic-info-card">
                    <h3 class="section-title">基础信息</h3>
                    <div class="basic-info-grid">
                        <div class="basic-info-item">
                            <div class="info-icon">⏰</div>
                            <div class="info-content">
                                <div class="info-label">烹饪时间</div>
                                <div class="info-value" id="recipe-modal-cooking-time">30分钟</div>
                            </div>
                        </div>
                        <div class="basic-info-item">
                            <div class="info-icon">🎯</div>
                            <div class="info-content">
                                <div class="info-label">难度</div>
                                <div class="info-value" id="recipe-modal-difficulty">中等</div>
                            </div>
                        </div>
                        <div class="basic-info-item">
                            <div class="info-icon">🍽️</div>
                            <div class="info-content">
                                <div class="info-label">分类</div>
                                <div class="info-value" id="recipe-modal-category"></div>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- 营养信息卡片 -->
                <div class="info-card nutrition-card">
                    <h3 class="section-title">营养信息</h3>
                    <div class="nutrition-grid">
                        <div class="nutrition-item">
                            <div class="nutrition-icon">🔥</div>
                            <div class="nutrition-content">
                                <div class="nutrition-label">热量</div>
                                <div class="nutrition-value" id="recipe-modal-calories"></div>
                            </div>
                        </div>
                        <div class="nutrition-item">
                            <div class="nutrition-icon">🌾</div>
                            <div class="nutrition-content">
                                <div class="nutrition-label">碳水</div>
                                <div class="nutrition-value" id="recipe-modal-carbs"></div>
                            </div>
                        </div>
                        <div class="nutrition-item">
                            <div class="nutrition-icon">💪</div>
                            <div class="nutrition-content">
                                <div class="nutrition-label">蛋白质</div>
                                <div class="nutrition-value" id="recipe-modal-protein"></div>
                            </div>
                        </div>
                        <div class="nutrition-item">
                            <div class="nutrition-icon">🥑</div>
                            <div class="nutrition-content">
                                <div class="nutrition-label">脂肪</div>
                                <div class="nutrition-value" id="recipe-modal-fat"></div>
                            </div>
                        </div>
                        <div class="nutrition-item">
                            <div class="nutrition-icon">💧</div>
                            <div class="nutrition-content">
                                <div class="nutrition-label">控油</div>
                                <div class="nutrition-value" id="recipe-modal-oil"></div>
                            </div>
                        </div>
                        <div class="nutrition-item">
                            <div class="nutrition-icon">📏</div>
                            <div class="nutrition-content">
                                <div class="nutrition-label">控量</div>
                                <div class="nutrition-value" id="recipe-modal-control"></div>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- 食材列表卡片 -->
                <div class="info-card ingredients-card">
                    <h3 class="section-title">食材</h3>
                    <div class="ingredients-grid" id="recipe-modal-ingredients"></div>
                </div>
                
                <!-- 步骤列表卡片 -->
                <div class="info-card steps-card">
                    <h3 class="section-title">烹饪步骤</h3>
                    <div class="steps-container" id="recipe-modal-steps"></div>
                </div>
                
                <!-- 食谱描述卡片 -->
                <div class="info-card description-card">
                    <h3 class="section-title">食谱描述</h3>
                    <div class="recipe-description" id="recipe-modal-description"></div>
                </div>
                
                <!-- 底部操作栏 -->
                <div class="footer-actions">
                    <button class="footer-btn" onclick="saveFavorite()">❤️ 收藏食谱</button>
                    <button class="footer-btn" onclick="copyRecipe()">📋 复制食谱</button>
                    <button class="footer-btn" onclick="shareRecipe()">📤 分享食谱</button>
                </div>
            </div>
        </div>
    </div>
    
    <!-- 健康目标模态框 -->
    <div id="health-goal-modal" class="modal">
        <div class="modal-content">
            <div class="modal-header">
                <div class="modal-title">健康目标设定</div>
                <span class="close-btn" onclick="closeHealthGoalModal()">&times;</span>
            </div>
            <div class="modal-body">
                <div class="step-title">请选择您的健康目标</div>
                <div class="options-container" id="health-goals-modal-container">
                    <!-- 健康目标选项将通过JavaScript动态生成 -->
                </div>
                <button class="btn btn-primary" onclick="setHealthGoal()">确定</button>
            </div>
        </div>
    </div>

    <!-- 数据页面 -->
    <div id="data-page" class="container">
        <div class="page-header">
            <button class="back-button" onclick="goBack('index')">返回</button>
            <div class="page-title">健康数据管理</div>
        </div>
        
        <!-- 标签页切换 -->
        <div class="tab-container">
            <div class="tab-item active" data-tab="record" onclick="switchTab(this)">记录数据</div>
            <div class="tab-item" data-tab="trend" onclick="switchTab(this)">数据趋势</div>
            <div class="tab-item" data-tab="rewards" onclick="switchTab(this)">非遗权益</div>
        </div>
        
        <!-- 记录数据 -->
        <div class="tab-content active" id="record-content">
            <div class="card">
                <div class="subtitle">饮食记录</div>
                
                <div class="form-item">
                    <div class="form-label">餐次</div>
                    <select class="picker" id="mealTypeSelect" onchange="selectMealType()">
                        <option value="">请选择餐次</option>
                        <option value="早餐">早餐</option>
                        <option value="午餐">午餐</option>
                        <option value="晚餐">晚餐</option>
                        <option value="加餐">加餐</option>
                    </select>
                </div>
                
                <div class="form-item">
                    <div class="form-label">食物类型</div>
                    <input class="input" placeholder="请输入食物类型" id="foodTypeInput" oninput="inputFoodType()">
                </div>
                
                <div class="form-button">
                    <button class="btn btn-primary" onclick="submitData()">提交记录</button>
                </div>
            </div>
            
            <div class="card">
                <div class="subtitle">餐具适配建议</div>
                <div class="adaptation-info">
                    <div class="info-card">
                        <div class="info-icon">💧</div>
                        <div class="info-content">
                            <div class="info-title">每餐控油</div>
                            <div class="info-value">10ml</div>
                        </div>
                    </div>
                    <div class="info-card">
                        <div class="info-icon">🍽️</div>
                        <div class="info-content">
                            <div class="info-title">每餐控量</div>
                            <div class="info-value">350ml</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- 数据趋势 -->
        <div class="tab-content" id="trend-content">
            <div class="card">
                <div class="subtitle">控油趋势</div>
                <div class="chart-container">
                    <canvas id="oilTrendChart" class="chart"></canvas>
                </div>
                <div class="chart-info">
                    <div class="chart-stat">
                        <div class="stat-label">本周累计控油</div>
                        <div class="stat-value color-health">73ml</div>
                    </div>
                    <div class="chart-stat">
                        <div class="stat-label">日均控油</div>
                        <div class="stat-value color-health">10.4ml</div>
                    </div>
                </div>
            </div>
            
            <div class="card">
                <div class="subtitle">健康统计</div>
                <div class="stats-grid">
                    <div class="stat-item">
                        <div class="stat-number">21</div>
                        <div class="stat-desc">连续记录天数</div>
                    </div>
                    <div class="stat-item">
                        <div class="stat-number">150</div>
                        <div class="stat-desc">累计记录次数</div>
                    </div>
                    <div class="stat-item">
                        <div class="stat-number">500</div>
                        <div class="stat-desc">累计控油(ml)</div>
                    </div>
                    <div class="stat-item">
                        <div class="stat-number">3</div>
                        <div class="stat-desc">达成健康目标</div>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- 非遗权益 -->
        <div class="tab-content" id="rewards-content">
            <div class="subtitle">非遗权益</div>
            <div class="rewards-list" id="rewards-list">
                <!-- 权益列表将通过JavaScript动态生成 -->
            </div>
            
            <div class="tips">
                <div class="tips-icon">💡</div>
                <div class="tips-text">完成健康目标，解锁更多非遗权益！</div>
            </div>
        </div>
        
        <!-- 权益兑换弹窗 -->
        <div class="reward-overlay" id="reward-overlay" onclick="closeRewardDetail()"></div>
        <div class="reward-popup" id="reward-popup">
            <div class="popup-header">
                <div class="popup-title" id="popup-title"></div>
                <div class="popup-close" onclick="closeRewardDetail()">×</div>
            </div>
            <div class="popup-content">
                <div class="reward-image">
                    <img id="reward-image" src="" alt="权益图片">
                </div>
                <div class="reward-info">
                    <div class="info-item">
                        <span class="info-label">描述：</span>
                        <span class="info-value" id="reward-description"></span>
                    </div>
                    <div class="info-item">
                        <span class="info-label">解锁条件：</span>
                        <span class="info-value" id="reward-requirement"></span>
                    </div>
                    <div class="info-item" id="redeem-code-container" style="display: none;">
                        <span class="info-label">兑换码：</span>
                        <span class="info-value redeem-code" id="redeem-code"></span>
                    </div>
                </div>
            </div>
            <div class="popup-footer">
                <button class="btn btn-primary" onclick="generateRedeemCode()" id="generate-btn">生成兑换码</button>
                <button class="btn btn-secondary" onclick="copyRedeemCode()" id="copy-btn" style="display: none;">复制兑换码</button>
            </div>
        </div>
    </div>
    
    <script>
        // 全局数据，从app.js迁移过来
        // 使用app.js中的全局数据
        const globalData = window.appData || {
            healthGoals: ['减脂', '控糖', '控盐', '增肌', '均衡饮食'],
            majiayaoPatterns: ['漩涡纹', '波浪纹', '圆点纹', '锯齿纹', '蛙纹', '菱格纹'],
            recipes: [
                {
                    id: 1,
                    title: '陇西腊肉蔬菜卷',
                    type: '减脂',
                    description: '传统陇西腊肉配以新鲜蔬菜，低热量高蛋白的健康选择',
                    ingredients: ['陇西腊肉100g', '黄瓜1根', '胡萝卜1根', '生菜适量', '全麦卷饼2张'],
                    steps: ['将黄瓜、胡萝卜切丝', '生菜洗净备用', '全麦卷饼加热', '将腊肉和蔬菜卷入口中'],
                    calories: 350,
                    carbs: 30,
                    protein: 25,
                    fat: 15,
                    control: '正常',
                    isGansuSpecial: true
                },
                {
                    id: 2,
                    title: '清蒸黄河鲤鱼',
                    type: '控糖',
                    description: '新鲜黄河鲤鱼清蒸，保留原汁原味，低糖高蛋白',
                    ingredients: ['黄河鲤鱼1条', '姜适量', '葱适量', '料酒适量', '盐适量', '糙米饭100g'],
                    steps: ['鲤鱼处理干净', '姜葱切丝铺在鱼身上', '淋上料酒和盐', '蒸锅上汽后蒸15分钟', '出锅后淋上热油'],
                    calories: 420,
                    carbs: 20,
                    protein: 40,
                    fat: 20,
                    control: '低糖',
                    isGansuSpecial: true
                },
                {
                    id: 3,
                    title: '牛肉蔬菜锅',
                    type: '增肌',
                    description: '精选牛肉搭配多种蔬菜，高蛋白高纤维，适合增肌人群',
                    ingredients: ['牛肉200g', '西兰花1朵', '土豆150g', '洋葱适量', '胡萝卜适量'],
                    steps: ['牛肉切片', '蔬菜切块', '锅中加水烧开', '放入所有食材煮熟', '加盐调味'],
                    calories: 500,
                    carbs: 45,
                    protein: 35,
                    fat: 25,
                    control: '高蛋白'
                },
                {
                    id: 4,
                    title: '荞面饸饹',
                    type: '控糖',
                    description: '传统荞面制作，低GI值，适合控糖人群',
                    ingredients: ['荞面200g', '羊肉汤适量', '香菜适量', '蒜苗适量'],
                    steps: ['荞面加水揉成面团', '压制成饸饹', '煮熟后捞出', '浇上羊肉汤，撒上香菜蒜苗'],
                    calories: 380,
                    carbs: 60,
                    protein: 12,
                    fat: 8,
                    control: '低糖',
                    isGansuSpecial: true
                },
                {
                    id: 5,
                    title: '藜麦沙拉',
                    type: '减脂',
                    description: '营养丰富的藜麦配以新鲜蔬果，低热量高纤维',
                    ingredients: ['藜麦100g', '鸡胸肉150g', '小番茄适量', '黄瓜适量', '橄榄油适量', '醋适量'],
                    steps: ['藜麦洗净煮熟', '鸡胸肉煎熟切块', '蔬菜洗净切块', '混合所有食材，加入橄榄油和醋调味'],
                    calories: 320,
                    carbs: 25,
                    protein: 28,
                    fat: 12,
                    control: '低热量'
                },
                {
                    id: 6,
                    title: '百合莲子粥',
                    type: '控盐',
                    description: '润肺养颜的百合莲子粥，清淡可口，适合控盐人群',
                    ingredients: ['百合50g', '莲子50g', '大米100g', '冰糖适量'],
                    steps: ['百合莲子洗净', '大米洗净', '所有食材放入锅中加水煮至软烂', '加冰糖调味'],
                    calories: 280,
                    carbs: 65,
                    protein: 6,
                    fat: 1,
                    control: '低钠'
                },
                {
                    id: 7,
                    title: '土豆烧牛肉',
                    type: '增肌',
                    description: '经典家常菜，土豆和牛肉的完美搭配，高蛋白高热量',
                    ingredients: ['牛肉300g', '土豆200g', '胡萝卜适量', '洋葱适量', '料酒适量', '酱油适量'],
                    steps: ['牛肉切块焯水', '土豆胡萝卜切块', '锅中放油爆香洋葱', '加入牛肉翻炒', '加入土豆胡萝卜和适量水', '炖煮至软烂'],
                    calories: 550,
                    carbs: 45,
                    protein: 40,
                    fat: 30,
                    control: '高蛋白'
                },
                {
                    id: 8,
                    title: '凉拌沙葱',
                    type: '控盐',
                    description: '西北特色凉拌菜，清爽可口，低钠健康',
                    ingredients: ['沙葱200g', '大蒜适量', '醋适量', '生抽少量', '香油适量', '玉米1根'],
                    steps: ['沙葱洗净切段', '大蒜切末', '加入醋、生抽、香油调味', '拌匀即可食用'],
                    calories: 180,
                    carbs: 25,
                    protein: 5,
                    fat: 8,
                    control: '低钠',
                    isGansuSpecial: true
                },
                {
                    id: 9,
                    title: '凉拌菠菜',
                    type: '减脂',
                    description: '简单的凉拌菠菜，低热量高营养，适合减脂人群',
                    ingredients: ['菠菜300g', '花生适量', '蒜适量', '醋适量', '生抽少量', '小米粥150ml'],
                    steps: ['菠菜焯水过凉', '花生炒熟碾碎', '蒜切末', '加入调料拌匀即可'],
                    calories: 200,
                    carbs: 25,
                    protein: 8,
                    fat: 10,
                    control: '低热量'
                },
                {
                    id: 10,
                    title: '番茄鸡蛋面',
                    type: '均衡饮食',
                    description: '经典的番茄鸡蛋面，营养均衡，适合日常食用',
                    ingredients: ['面条150g', '番茄2个', '鸡蛋2个', '青菜适量', '盐适量'],
                    steps: ['番茄切块', '鸡蛋打散炒熟', '锅中放油炒番茄', '加入鸡蛋和水', '面条煮熟后加入', '最后加入青菜'],
                    calories: 400,
                    carbs: 60,
                    protein: 15,
                    fat: 10,
                    control: '正常'
                },
                {
                    id: 11,
                    title: '甘肃浆水面',
                    type: '控糖',
                    description: '甘肃特色美食，酸甜开胃，低热量低GI值，适合控糖人群',
                    ingredients: ['面条150g', '浆水菜200g', '香菜适量', '蒜苗适量', '辣椒油适量'],
                    steps: ['将浆水菜洗净', '锅中加水烧开，加入浆水菜', '面条煮熟后捞出', '浇上浆水汤', '撒上香菜蒜苗，加入辣椒油'],
                    calories: 320,
                    carbs: 50,
                    protein: 10,
                    fat: 8,
                    control: '低糖',
                    isGansuSpecial: true
                },
                {
                    id: 12,
                    title: '黄芪鸡汤',
                    type: '均衡饮食',
                    description: '传统黄芪鸡汤，补气养血，营养丰富',
                    ingredients: ['鸡肉500g', '黄芪10g', '党参5g', '红枣适量', '姜片适量', '面条100g'],
                    steps: ['鸡肉焯水', '所有食材放入锅中', '加水炖煮1.5小时', '加盐调味'],
                    calories: 450,
                    carbs: 10,
                    protein: 50,
                    fat: 25,
                    control: '正常'
                },
                {
                    id: 12,
                    title: '银耳百合羹',
                    type: '控糖',
                    description: '滋阴润肺的银耳百合羹，低糖健康',
                    ingredients: ['银耳10g', '百合20g', '莲子10g', '枸杞适量', '燕麦20g'],
                    steps: ['银耳泡发撕小朵', '百合莲子洗净', '所有食材放入锅中加水炖煮1小时', '可加少量冰糖调味'],
                    calories: 220,
                    carbs: 45,
                    protein: 5,
                    fat: 2,
                    control: '低糖'
                }
            ],
            // 模拟周控油数据
            weeklyOilData: [
              { day: '周一', oil: 5 },
              { day: '周二', oil: 12 },
              { day: '周三', oil: 10 },
              { day: '周四', oil: 8 },
              { day: '周五', oil: 11 },
              { day: '周六', oil: 9 },
              { day: '周日', oil: 7 }
            ],
            // 非遗权益
            rewards: [
              {
                id: 1,
                title: '免费刻字升级',
                description: '连续使用1个月即可解锁',
                requirement: '连续使用30天',
                image: '/images/reward1.png'
              },
              {
                id: 2,
                title: '非遗手作兑换券',
                description: '累计控油500ml即可解锁',
                requirement: '累计控油500ml',
                image: '/images/reward2.png'
              },
              {
                id: 3,
                title: '马家窑纹样定制',
                description: '完成3个健康目标即可解锁',
                requirement: '完成3个健康目标',
                image: '/images/reward3.png'
              }
            ]
        };
        
        // 页面状态
        let currentPage = 'index';
        let currentStep = 1;
        let selectedGoal = '';
        let selectedPattern = '';
        let customPattern = '';
        let customPatternImage = '';
        
        // 预设的纹样组合
        const patternCombinations = {
            '减脂': '漩涡纹+蛙纹',
            '控糖': '波浪纹+圆点纹',
            '控盐': '锯齿纹+漩涡纹',
            '增肌': '蛙纹+菱格纹',
            '均衡饮食': '圆点纹+波浪纹'
        };
        
        // 预设的纹样图片
        const patternImages = {
            '漩涡纹+蛙纹': 'https://images.unsplash.com/photo-1518444065439-e933c06ce9cd?w=400&h=400&fit=crop',
            '波浪纹+圆点纹': 'https://images.unsplash.com/photo-1589998059171-988d887df646?w=400&h=400&fit=crop',
            '锯齿纹+漩涡纹': 'https://images.unsplash.com/photo-1600013641121-5d127daa44fe?w=400&h=400&fit=crop',
            '蛙纹+菱格纹': 'https://images.unsplash.com/photo-1579683000905-4c2440b13a11?w=400&h=400&fit=crop',
            '圆点纹+波浪纹': 'https://images.unsplash.com/photo-1565075143130-b18101172358?w=400&h=400&fit=crop'
        };
        
        // 数据页面相关变量
        let currentTab = 'record';
        let mealType = '';
        let foodType = '';
        let showRedeem = false;
        let currentReward = null;
        let redeemCode = '';

        // 页面加载完成后初始化
        document.addEventListener('DOMContentLoaded', function() {
            loadRecipes();
            renderHealthGoals();
            renderPatterns();
            renderHealthGoalsModal();
            // 初始化数据页面
            generateRewards();
            drawOilTrendChart();
        });
        
        // 加载食谱列表
        function loadRecipes() {
            const recipeList = document.getElementById('recipe-list');
            recipeList.innerHTML = '';
            
            globalData.recipes.forEach(recipe => {
                const recipeItem = document.createElement('div');
                recipeItem.className = 'recipe-card';
                recipeItem.onclick = () => showRecipeDetail(recipe);
                
                // 使用食谱全称作为显示
                
                recipeItem.innerHTML = `
                    <div class="recipe-image">
                        <div class="recipe-placeholder">${recipe.title}</div>
                        <div class="recipe-type-badge">${recipe.type}</div>
                        ${recipe.isGansuSpecial ? '<div class="gansu-special">🍜</div>' : ''}
                    </div>
                    <div class="recipe-content">
                        <div class="recipe-title">${recipe.title}</div>
                        <div class="recipe-meta">
                            <div class="meta-item">⏰ ${recipe.cookingTime || '30分钟'}</div>
                            <div class="meta-item">🎯 ${recipe.difficulty || '中等'}</div>
                        </div>
                        <div class="nutrition-info">
                            <div class="nutrition-item">
                                <span class="nutrition-label">热量</span>
                                <span class="nutrition-value">${recipe.calories}kcal</span>
                            </div>
                            <div class="nutrition-item">
                                <span class="nutrition-label">控油</span>
                                <span class="nutrition-value">${recipe.oilControl || '中等'}</span>
                            </div>
                            <div class="nutrition-item">
                                <span class="nutrition-label">控量</span>
                                <span class="nutrition-value">${recipe.portionControl || '适中'}</span>
                            </div>
                        </div>
                        <div class="recipe-tags">
                            <span class="tag calorie-tag">${recipe.calories}kcal</span>
                            <span class="tag protein-tag">${recipe.protein}g</span>
                        </div>
                    </div>
                `;
                
                recipeList.appendChild(recipeItem);
            });
        }
        
        // 渲染健康目标选项
        function renderHealthGoals() {
            const container = document.getElementById('health-goals-container');
            container.innerHTML = '';
            
            globalData.healthGoals.forEach(goal => {
                const optionItem = document.createElement('div');
                optionItem.className = 'option-item';
                optionItem.onclick = () => selectGoal(goal);
                
                optionItem.innerHTML = `
                    <div class="option-text">${goal}</div>
                    <div class="option-check" style="display: none;">✓</div>
                `;
                
                container.appendChild(optionItem);
            });
        }
        
        // 渲染纹样选项
        function renderPatterns() {
            const container = document.getElementById('patterns-container');
            container.innerHTML = '';
            
            globalData.majiayaoPatterns.forEach(pattern => {
                const patternItem = document.createElement('div');
                patternItem.className = 'pattern-item';
                patternItem.onclick = () => selectPattern(pattern);
                
                patternItem.innerHTML = `
                    <div class="pattern-icon">🎨</div>
                    <div class="pattern-name">${pattern}</div>
                    <div class="pattern-check" style="display: none;">✓</div>
                `;
                
                container.appendChild(patternItem);
            });
        }
        
        // 渲染健康目标模态框选项
        function renderHealthGoalsModal() {
            const container = document.getElementById('health-goals-modal-container');
            container.innerHTML = '';
            
            globalData.healthGoals.forEach(goal => {
                const optionItem = document.createElement('div');
                optionItem.className = 'option-item';
                optionItem.onclick = (e) => selectGoalModal(goal, e);
                
                optionItem.innerHTML = `
                    <div class="option-text">${goal}</div>
                    <div class="option-check" style="display: none;">✓</div>
                `;
                
                container.appendChild(optionItem);
            });
        }
        
        // 页面导航
        function goToRecipePage() {
            hideAllPages();
            document.getElementById('recipe-page').style.display = 'block';
            currentPage = 'recipe';
        }
        
        function goToCustomizePage() {
            hideAllPages();
            document.getElementById('customize-page').style.display = 'block';
            currentPage = 'customize';
        }
        
        function goBack(page) {
            hideAllPages();
            document.getElementById(`${page}-page`).style.display = 'block';
            currentPage = page;
            
            // 重置定制页面状态
            if (page === 'index') {
                restartCustomize();
            }
        }
        
        function hideAllPages() {
            document.getElementById('index-page').style.display = 'none';
            document.getElementById('recipe-page').style.display = 'none';
            document.getElementById('customize-page').style.display = 'none';
        }
        
        // 食谱筛选
        function filterRecipes(button) {
            // 移除所有按钮的active类
            document.querySelectorAll('.filter-btn').forEach(btn => {
                btn.classList.remove('active');
            });
            
            // 给当前按钮添加active类
            button.classList.add('active');
            
            const filter = button.getAttribute('data-filter');
            const recipeItems = document.querySelectorAll('.recipe-card');
            
            recipeItems.forEach(item => {
                const recipeType = item.querySelector('.recipe-type-badge').textContent.trim();
                if (filter === 'all' || recipeType.toLowerCase() === filter.toLowerCase()) {
                    item.style.display = 'flex';
                } else {
                    item.style.display = 'none';
                }
            });
        }
        
        // 清除筛选条件
        function clearFilter() {
            try {
                // 移除所有按钮的active类
                document.querySelectorAll('.filter-btn').forEach(btn => {
                    btn.classList.remove('active');
                });
                
                // 激活"全部"按钮
                const allBtn = document.querySelector('.filter-btn[data-filter="all"]');
                if (allBtn) {
                    allBtn.classList.add('active');
                }
                
                // 显示所有食谱
                const recipeItems = document.querySelectorAll('.recipe-card');
                recipeItems.forEach(item => {
                    item.style.display = 'flex';
                });
                
                alert('筛选条件已清除');
            } catch (error) {
                console.error('清除筛选条件时出错:', error);
            }
        }
        
        // 当前显示的食谱
        let currentRecipe = null;
        
        // 显示食谱详情
        function showRecipeDetail(recipe) {
            currentRecipe = recipe;
            // 设置食谱基本信息
            document.getElementById('recipe-modal-title').textContent = recipe.title;
            document.getElementById('recipe-modal-type').textContent = recipe.type;
            document.getElementById('recipe-modal-calories').textContent = `${recipe.calories}kcal`;
            document.getElementById('recipe-modal-carbs').textContent = `${recipe.carbs || 0}g`;
            document.getElementById('recipe-modal-protein').textContent = `${recipe.protein}g`;
            document.getElementById('recipe-modal-fat').textContent = `${recipe.fat || 0}g`;
            document.getElementById('recipe-modal-oil').textContent = recipe.oilControl || '中等';
            document.getElementById('recipe-modal-control').textContent = recipe.portionControl || '适中';
            document.getElementById('recipe-modal-description').textContent = recipe.description;
            document.getElementById('recipe-modal-cooking-time').textContent = recipe.cookingTime || '30分钟';
            document.getElementById('recipe-modal-difficulty').textContent = recipe.difficulty || '中等';
            document.getElementById('recipe-modal-category').textContent = recipe.type;
            
            // 设置食谱图片占位符，显示食谱全称
            document.getElementById('recipe-modal-placeholder').textContent = recipe.title;
            
            // 显示/隐藏甘肃特色标识
            const gansuElement = document.getElementById('recipe-modal-gansu');
            if (recipe.isGansuSpecial) {
                gansuElement.style.display = 'flex';
            } else {
                gansuElement.style.display = 'none';
            }
            
            // 更新食材列表（使用标签式布局）
            const ingredientsList = document.getElementById('recipe-modal-ingredients');
            ingredientsList.innerHTML = '';
            
            // 添加默认食材（如果食谱中没有提供）
            const ingredients = recipe.ingredients || ['主要食材1 适量', '主要食材2 适量', '主要食材3 适量'];
            ingredients.forEach(ingredient => {
                const ingredientTag = document.createElement('div');
                ingredientTag.className = 'ingredient-tag';
                ingredientTag.textContent = ingredient;
                ingredientsList.appendChild(ingredientTag);
            });
            
            // 更新步骤列表（使用卡片式布局）
            const stepsList = document.getElementById('recipe-modal-steps');
            stepsList.innerHTML = '';
            
            // 添加默认步骤（如果食谱中没有提供）
            const steps = recipe.steps || ['准备好所有食材', '按照步骤进行烹饪', '完成后即可享用'];
            steps.forEach((step, index) => {
                const stepCard = document.createElement('div');
                stepCard.className = 'step-card';
                
                stepCard.innerHTML = `
                    <div class="step-number">${index + 1}</div>
                    <div class="step-content">${step}</div>
                `;
                
                stepsList.appendChild(stepCard);
            });
            
            // 显示模态框
            document.getElementById('recipe-modal').style.display = 'flex';
        }
        
        // 关闭食谱详情模态框
        function closeRecipeModal() {
            document.getElementById('recipe-modal').style.display = 'none';
            currentRecipe = null;
        }
        
        // 分享食谱
        function shareRecipe() {
            if (!currentRecipe) {
                alert('没有找到要分享的食谱');
                return;
            }
            
            // 这里可以实现分享功能，目前使用alert模拟
            alert('分享功能开发中，敬请期待！');
        }
        
        // 收藏食谱
        function saveFavorite() {
            if (!currentRecipe) {
                alert('没有找到要收藏的食谱');
                return;
            }
            
            try {
                // 从localStorage获取收藏列表
                let favorites = JSON.parse(localStorage.getItem('favorites')) || [];
                
                // 检查是否已经收藏
                const isFavorited = favorites.some(recipe => recipe.id === currentRecipe.id);
                if (isFavorited) {
                    alert('该食谱已经在收藏列表中');
                    return;
                }
                
                // 添加到收藏列表
                favorites.push(currentRecipe);
                localStorage.setItem('favorites', JSON.stringify(favorites));
                
                alert('食谱收藏成功！');
            } catch (error) {
                console.error('收藏食谱时出错:', error);
                alert('收藏失败，请重试');
            }
        }
        
        // 复制食谱
        function copyRecipe() {
            if (!currentRecipe) {
                alert('没有找到要复制的食谱');
                return;
            }
            
            try {
                // 构建食谱文本
                let recipeText = `【${currentRecipe.title}】\n\n`;
                recipeText += `类型：${currentRecipe.type}\n`;
                recipeText += `热量：${currentRecipe.calories}kcal\n`;
                recipeText += `碳水：${currentRecipe.carbs}g\n`;
                recipeText += `蛋白质：${currentRecipe.protein}g\n`;
                recipeText += `脂肪：${currentRecipe.fat}g\n`;
                recipeText += `控量：${currentRecipe.control}\n\n`;
                recipeText += `描述：${currentRecipe.description}\n\n`;
                recipeText += `食材：\n${currentRecipe.ingredients.join('\n')}\n\n`;
                recipeText += `步骤：\n${currentRecipe.steps.map((step, index) => `${index + 1}. ${step}`).join('\n')}`;
                
                // 使用现代剪贴板API
                if (navigator.clipboard && window.isSecureContext) {
                    navigator.clipboard.writeText(recipeText).then(() => {
                        alert('食谱已复制到剪贴板');
                    }).catch(err => {
                        console.error('剪贴板写入失败:', err);
                        fallbackCopy(recipeText);
                    });
                } else {
                    fallbackCopy(recipeText);
                }
            } catch (error) {
                console.error('复制食谱时出错:', error);
                alert('复制失败，请重试');
            }
        }
        
        // 兼容老浏览器的复制方法
        function fallbackCopy(text) {
            const textArea = document.createElement('textarea');
            textArea.value = text;
            textArea.style.position = 'fixed';
            textArea.style.left = '-999999px';
            textArea.style.top = '-999999px';
            document.body.appendChild(textArea);
            textArea.focus();
            textArea.select();
            
            try {
                document.execCommand('copy');
                alert('食谱已复制到剪贴板');
            } catch (err) {
                console.error('复制失败:', err);
                alert('复制失败，请手动复制');
            } finally {
                document.body.removeChild(textArea);
            }
        }
        
        // 显示健康目标模态框
        function showHealthGoalModal(e) {
            // 确保只有通过明确的点击事件才能显示模态框
            if (e && e.type === 'click') {
                document.getElementById('health-goal-modal').style.display = 'block';
            } else {
                console.log('拒绝非点击触发的健康目标模态框显示');
            }
        }
        
        // 关闭健康目标模态框
        function closeHealthGoalModal() {
            document.getElementById('health-goal-modal').style.display = 'none';
        }
        
        // 扫码功能
        function scanCode() {
            // 更友好的扫码模拟
            if (confirm('是否开启摄像头进行扫码？')) {
                setTimeout(() => {
                    alert('扫码成功！\n餐具ID: MJY-20240515-001\n已成功绑定');
                }, 1000);
            }
        }
        
        // 扫码并进入下一步
        function scanCodeAndNext() {
            if (confirm('是否开启摄像头进行扫码？')) {
                setTimeout(() => {
                    alert('扫码成功！\n餐具ID: MJY-20240515-001\n已成功绑定');
                    nextStep();
                }, 1000);
            }
        }
        
        // 选择健康目标
        function selectGoal(goal) {
            selectedGoal = goal;
            
            // 更新选项状态
            document.querySelectorAll('.option-item').forEach(item => {
                const optionText = item.querySelector('.option-text').textContent;
                const checkMark = item.querySelector('.option-check');
                
                if (optionText === goal) {
                    item.classList.add('selected');
                    checkMark.style.display = 'block';
                } else {
                    item.classList.remove('selected');
                    checkMark.style.display = 'none';
                }
            });
        }
        
        // 选择纹样
        function selectPattern(pattern) {
            selectedPattern = pattern;
            
            // 更新选项状态
            document.querySelectorAll('.pattern-item').forEach(item => {
                const patternName = item.querySelector('.pattern-name').textContent;
                const checkMark = item.querySelector('.pattern-check');
                
                if (patternName === pattern) {
                    item.classList.add('selected');
                    checkMark.style.display = 'block';
                } else {
                    item.classList.remove('selected');
                    checkMark.style.display = 'none';
                }
            });
        }
        
        // 选择健康目标模态框选项
        function selectGoalModal(goal, event) {
            // 移除所有选中状态
            document.querySelectorAll('#health-goals-modal-container .option-item').forEach(item => {
                item.classList.remove('selected');
                item.querySelector('.option-check').style.display = 'none';
            });
            
            // 选中当前目标
            const selectedItem = event.target.closest('.option-item');
            if (selectedItem) {
                selectedItem.classList.add('selected');
                selectedItem.querySelector('.option-check').style.display = 'block';
            }
            
            selectedGoal = goal;
        }
        
        // 设置健康目标
        function setHealthGoal() {
            if (selectedGoal) {
                alert(`健康目标已设定为：${selectedGoal}`);
                closeHealthGoalModal();
            } else {
                alert('请选择健康目标');
            }
        }
        
        // 下一步
        function nextStep() {
            if (currentStep === 1) {
                // 从步骤1到步骤2
                hideAllSteps();
                document.getElementById('step-content-2').style.display = 'block';
                updateProgress(2);
                currentStep = 2;
            } else if (currentStep === 2) {
                // 从步骤2到步骤3
                if (!selectedGoal) {
                    alert('请选择健康目标');
                    return;
                }
                
                hideAllSteps();
                document.getElementById('step-content-3').style.display = 'block';
                updateProgress(3);
                currentStep = 3;
            } else if (currentStep === 3) {
                // 从步骤3到步骤4
                if (!selectedPattern) {
                    alert('请选择马家窑纹样');
                    return;
                }
                
                // 生成专属纹样
                generatePattern();
                
                hideAllSteps();
                document.getElementById('step-content-4').style.display = 'block';
                updateProgress(4);
                currentStep = 4;
            }
        }
        
        // 上一步
        function prevStep() {
            if (currentStep === 2) {
                // 从步骤2到步骤1
                hideAllSteps();
                document.getElementById('step-content-1').style.display = 'block';
                updateProgress(1);
                currentStep = 1;
            } else if (currentStep === 3) {
                // 从步骤3到步骤2
                hideAllSteps();
                document.getElementById('step-content-2').style.display = 'block';
                updateProgress(2);
                currentStep = 2;
            } else if (currentStep === 4) {
                // 从步骤4到步骤3
                hideAllSteps();
                document.getElementById('step-content-3').style.display = 'block';
                updateProgress(3);
                currentStep = 3;
            }
        }
        
        // 隐藏所有步骤
        function hideAllSteps() {
            for (let i = 1; i <= 4; i++) {
                document.getElementById(`step-content-${i}`).style.display = 'none';
            }
        }
        
        // 更新进度指示器
        function updateProgress(step) {
            // 更新步骤点
            for (let i = 1; i <= 4; i++) {
                const stepElement = document.getElementById(`step-${i}`);
                const labelElement = document.querySelectorAll('.progress-label')[i-1];
                
                if (i <= step) {
                    stepElement.classList.add('active');
                    labelElement.classList.add('active');
                } else {
                    stepElement.classList.remove('active');
                    labelElement.classList.remove('active');
                }
            }
            
            // 更新进度线
            for (let i = 1; i <= 3; i++) {
                const lineElement = document.getElementById(`line-${i}`);
                if (i < step) {
                    lineElement.classList.add('active');
                } else {
                    lineElement.classList.remove('active');
                }
            }
        }
        
        // 生成专属纹样
        function generatePattern() {
            // 根据健康目标和选择的纹样生成专属组合
            if (selectedGoal && selectedPattern) {
                customPattern = `${selectedGoal}-${selectedPattern}`;
                // 使用更丰富的纹样生成逻辑
                customPatternImage = patternImages[customPattern] || 
                                     `https://via.placeholder.com/400?text=${encodeURIComponent(customPattern)}`;
            } else {
                customPattern = '自定义纹样';
                customPatternImage = 'https://via.placeholder.com/400';
            }
            
            // 更新预览
            document.getElementById('custom-pattern').textContent = customPattern;
            document.getElementById('custom-pattern-image').src = customPatternImage;
            document.getElementById('selected-goal-text').textContent = selectedGoal;
            document.getElementById('selected-pattern-text').textContent = selectedPattern;
        }
        
        // 重新定制
        function restartCustomize() {
            // 重置状态
            currentStep = 1;
            selectedGoal = '';
            selectedPattern = '';
            customPattern = '';
            customPatternImage = '';
            
            // 重置UI
            hideAllSteps();
            document.getElementById('step-content-1').style.display = 'block';
            updateProgress(1);
            
            // 重置选择状态
            document.querySelectorAll('.option-item.selected').forEach(item => {
                item.classList.remove('selected');
                item.querySelector('.option-check').style.display = 'none';
            });
            
            document.querySelectorAll('.pattern-item.selected').forEach(item => {
                item.classList.remove('selected');
                item.querySelector('.pattern-check').style.display = 'none';
            });
            
            // 重置预览
            document.getElementById('custom-pattern').textContent = '';
            document.getElementById('custom-pattern-image').src = '';
            document.getElementById('selected-goal-text').textContent = '';
            document.getElementById('selected-pattern-text').textContent = '';
        }
        
        // 匹配食谱
        function matchRecipes() {
            if (!selectedGoal) {
                alert('请先完成定制');
                return;
            }
            
            // 切换到食谱页面
            goToRecipePage();
            
            // 自动筛选匹配的食谱
            const filterBtn = document.querySelector(`.filter-btn[data-filter="${selectedGoal}"]`);
            if (filterBtn) {
                filterRecipes(filterBtn);
            }
            
            alert(`正在为您匹配${selectedGoal}食谱...`);
        }
        
        // 完成定制
        function completeCustomize() {
            alert('您的专属纹样已生成，感谢使用！');
            goBack('index');
        }
        
        // 点击模态框外部关闭
        window.onclick = function(event) {
            const recipeModal = document.getElementById('recipe-modal');
            const healthGoalModal = document.getElementById('health-goal-modal');
            
            if (event.target === recipeModal) {
                recipeModal.style.display = 'none';
            }
            
            if (event.target === healthGoalModal) {
                healthGoalModal.style.display = 'none';
            }
        }
        
        // ESC键关闭模态框
        window.addEventListener('keydown', function(event) {
            if (event.key === 'Escape') {
                document.getElementById('recipe-modal').style.display = 'none';
                document.getElementById('health-goal-modal').style.display = 'none';
                document.getElementById('reward-popup').style.display = 'none';
                document.getElementById('reward-overlay').style.display = 'none';
            }
        });

        // 数据页面导航
        function goToDataPage() {
            // 跳转到单独的数据页面
            window.location.href = 'data.html';
        }

        // 切换标签页
        function switchTab(tabElement) {
            // 移除所有标签的激活状态
            const tabItems = document.querySelectorAll('.tab-item');
            tabItems.forEach(item => item.classList.remove('active'));
            
            // 添加当前标签的激活状态
            tabElement.classList.add('active');
            
            // 切换内容
            const tab = tabElement.dataset.tab;
            const tabContents = document.querySelectorAll('.tab-content');
            tabContents.forEach(content => content.classList.remove('active'));
            
            document.getElementById(`${tab}-content`).classList.add('active');
            
            // 如果切换到趋势页，重新绘制图表
            if (tab === 'trend') {
                setTimeout(function() {
                    drawOilTrendChart();
                }, 100);
            }
        }

        // 选择餐次
        function selectMealType() {
            const selectElement = document.getElementById('mealTypeSelect');
            mealType = selectElement.value;
        }

        // 输入食物类型
        function inputFoodType() {
            const inputElement = document.getElementById('foodTypeInput');
            foodType = inputElement.value;
        }

        // 提交数据
        function submitData() {
            if (!mealType || !foodType) {
                alert('请填写完整信息');
                return;
            }
            
            // 模拟数据提交
            alert('记录成功');
            
            // 重置表单
            document.getElementById('mealTypeSelect').value = '';
            document.getElementById('foodTypeInput').value = '';
            mealType = '';
            foodType = '';
            
            // 模拟更新控油数据
            updateOilData();
        }

        // 更新控油数据（模拟）
        function updateOilData() {
            const randomOil = Math.floor(Math.random() * 15) + 5;
            const today = new Date().getDay();
            
            const updatedData = [...globalData.weeklyOilData];
            updatedData[today].oil = randomOil;
            
            // 重新绘制图表
            drawOilTrendChart();
        }

        // 绘制控油趋势图
        function drawOilTrendChart() {
            const canvas = document.getElementById('oilTrendChart');
            const ctx = canvas.getContext('2d');
            const data = globalData.weeklyOilData;
            
            // 设置画布尺寸
            canvas.width = canvas.offsetWidth;
            canvas.height = canvas.offsetHeight;
            const canvasWidth = canvas.width;
            const canvasHeight = canvas.height;
            
            // 计算最大控油值，用于缩放图表
            const maxOil = Math.max(...data.map(item => item.oil)) * 1.2;
            
            // 绘制背景
            ctx.fillStyle = '#fff';
            ctx.fillRect(0, 0, canvasWidth, canvasHeight);
            
            // 绘制网格线
            ctx.strokeStyle = '#eee';
            ctx.lineWidth = 1;
            
            // 水平线
            for (let i = 0; i <= 4; i++) {
                const y = canvasHeight - (canvasHeight / 4) * i;
                ctx.beginPath();
                ctx.moveTo(40, y);
                ctx.lineTo(canvasWidth - 20, y);
                ctx.stroke();
                
                // 绘制数值标签
                ctx.fillStyle = '#999';
                ctx.font = '12px Arial';
                ctx.fillText(Math.round(maxOil * i / 4), 10, y + 5);
            }
            
            // 绘制数据线
            ctx.strokeStyle = '#3CC51F';
            ctx.lineWidth = 2;
            ctx.beginPath();
            
            data.forEach((item, index) => {
                const x = 40 + (canvasWidth - 60) / (data.length - 1) * index;
                const y = canvasHeight - (item.oil / maxOil) * canvasHeight;
                
                if (index === 0) {
                    ctx.moveTo(x, y);
                } else {
                    ctx.lineTo(x, y);
                }
                
                // 绘制数据点
                ctx.fillStyle = '#3CC51F';
                ctx.beginPath();
                ctx.arc(x, y, 3, 0, 2 * Math.PI);
                ctx.fill();
                
                // 绘制日期标签
                ctx.fillStyle = '#666';
                ctx.font = '12px Arial';
                ctx.fillText(item.day, x - 15, canvasHeight - 5);
            });
            
            ctx.stroke();
        }

        // 生成权益列表
        function generateRewards() {
            const rewardsList = document.getElementById('rewards-list');
            rewardsList.innerHTML = '';
            
            globalData.rewards.forEach(reward => {
                const rewardItem = document.createElement('div');
                rewardItem.className = 'reward-item card';
                rewardItem.dataset.id = reward.id;
                rewardItem.onclick = function() { viewRewardDetail(reward.id); };
                
                rewardItem.innerHTML = `
                    <div class="reward-header">
                        <div class="reward-icon">🏆</div>
                        <div class="reward-title">${reward.title}</div>
                    </div>
                    <div class="reward-description">${reward.description}</div>
                    <div class="reward-requirement">
                        <span class="requirement-label">解锁条件：</span>
                        <span class="requirement-value">${reward.requirement}</span>
                    </div>
                    <div class="reward-status">
                        <div class="status-badge">已解锁</div>
                    </div>
                `;
                
                rewardsList.appendChild(rewardItem);
            });
        }

        // 查看权益详情
        function viewRewardDetail(rewardId) {
            currentReward = globalData.rewards.find(r => r.id === rewardId);
            
            if (currentReward) {
                // 更新弹窗内容
                document.getElementById('popup-title').textContent = currentReward.title;
                document.getElementById('reward-image').src = currentReward.image;
                document.getElementById('reward-description').textContent = currentReward.description;
                document.getElementById('reward-requirement').textContent = currentReward.requirement;
                
                // 显示弹窗
                document.getElementById('reward-overlay').style.display = 'block';
                document.getElementById('reward-popup').style.display = 'block';
            }
        }

        // 关闭权益详情
        function closeRewardDetail() {
            // 隐藏弹窗
            document.getElementById('reward-overlay').style.display = 'none';
            document.getElementById('reward-popup').style.display = 'none';
            
            // 重置数据
            currentReward = null;
            redeemCode = '';
            document.getElementById('redeem-code-container').style.display = 'none';
            document.getElementById('generate-btn').style.display = 'block';
            document.getElementById('copy-btn').style.display = 'none';
        }

        // 生成兑换码
        function generateRedeemCode() {
            const chars = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789';
            let code = '';
            for (let i = 0; i < 8; i++) {
                code += chars.charAt(Math.floor(Math.random() * chars.length));
                if (i === 3) code += '-';
            }
            
            redeemCode = code;
            document.getElementById('redeem-code').textContent = redeemCode;
            document.getElementById('redeem-code-container').style.display = 'block';
            document.getElementById('generate-btn').style.display = 'none';
            document.getElementById('copy-btn').style.display = 'block';
            
            alert('兑换码已生成');
        }

        // 复制兑换码
        function copyRedeemCode() {
            if (!redeemCode) {
                alert('请先生成兑换码');
                return;
            }
            
            // 使用Web API复制到剪贴板
            navigator.clipboard.writeText(redeemCode)
                .then(function() {
                    alert('兑换码已复制');
                })
                .catch(function(err) {
                    console.error('复制失败:', err);
                    alert('复制失败，请手动复制');
                });
        }
    </script>
</body>
</html>
