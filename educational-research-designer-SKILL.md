---
name: educational-research-designer
description: Designs structured educational research proposals and instructional innovations. Use when the user asks to "design a research study", "draft a research proposal", "create a teaching model", "plan action research", or "help with classroom research". Automatically tailored for vocational and technology education contexts.
---

# Educational Research & Instructional Innovation Designer

## Overview
Develop a comprehensive, academically rigorous educational research proposal. The output should be clear, actionable, and ready for implementation in a vocational or technical education setting (e.g., IT and tech disciplines).

## Step 1: Establish the Research Context
Before generating the proposal, identify the following elements. If they are not clear from the user's prompt, explicitly ask the user for them:
- **The Core Problem:** What is the specific learning gap or technical skill deficiency?
- **The Intervention:** What instructional innovation, technology tool, or teaching method is being introduced?
- **Target Audience:** Specify the vocational level (e.g., ปวช., ปวส.) and specific technical discipline.

## Step 2: Formulate the Research Framework
Once context is gathered, develop the core components:
1.  **Research Title:** Must be formal and indicate the intervention, the target group, and the outcome.
2.  **Objectives:** Use action verbs (e.g., To develop, To compare, To evaluate). Limit to 2-3 measurable objectives.
3.  **Variables:** - **Independent Variable:** The instructional innovation or tool.
    - **Dependent Variable:** The learning outcomes, practical competencies, or student satisfaction.

## Step 3: Outline the Methodology
Define the research methodology clearly:
- **Population & Sample:** Define the sampling technique suitable for classroom settings.
- **Instruments:** List required tools (e.g., Competency-based lesson plans, practical IT/coding assessments, behavioral observation forms).
- **Data Collection & Analysis:** Specify the experimental design (e.g., One-Group Pretest-Posttest) and statistical tools (Mean, S.D., t-test dependent).

## Step 4: Generate the Proposal
Output the proposal strictly using the following Markdown structure:

```markdown
# 📑 โครงร่างงานวิจัย (Educational Research Proposal)

## 1. ชื่อเรื่องวิจัย (Research Title)
[Provide 2 formal options in Thai]

## 2. ความเป็นมาและความสำคัญของปัญหา (Background)
[Brief paragraph explaining the need for this innovation, emphasizing practical/vocational skill gaps.]

## 3. วัตถุประสงค์การวิจัย (Objectives)
1. [Objective 1]
2. [Objective 2]

## 4. กรอบแนวคิดการวิจัย (Conceptual Framework)
- **ตัวแปรต้น (Independent Variable):** [Variable]
- **ตัวแปรตาม (Dependent Variable):** [Variable]

## 5. วิธีดำเนินการวิจัย (Methodology)
- **กลุ่มเป้าหมาย:** [Target Group]
- **เครื่องมือที่ใช้:** [List of Instruments]
- **สถิติที่ใช้ในการวิเคราะห์ข้อมูล:** [Statistical Analysis]
```

## Step 5: Quality Check
Before finalizing the output, perform an internal verification:
- [ ] The description of the intervention is clear and practical for a tech/vocational education setting.
- [ ] The objectives are measurable and align precisely with the proposed instruments.
- [ ] The format strictly follows the provided Markdown template.
- [ ] No placeholder text like "[Objective 1]" is left in the final response.
