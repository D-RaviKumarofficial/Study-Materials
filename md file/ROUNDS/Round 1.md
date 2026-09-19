# Walmart AI/ML Engineer - Recruiter Screen (Round 1)
## Complete Question Bank with Expected Answers

**Duration:** 30 minutes
**Format:** Phone call with HR/Recruiter
**Difficulty:** Easy
**Purpose:** Screen for basic fit, enthusiasm, and communication skills

---

## 📋 TYPICAL RECRUITER SCREEN AGENDA

```
1. Introduction & Small Talk (2-3 min)
2. Resume Review & Experience Questions (8-10 min)
3. Motivation & Interest Questions (5-7 min)
4. Logistical Questions (3-5 min)
5. Your Questions (3-5 min)
```

---

## 🎯 ALL POSSIBLE QUESTIONS WITH ANSWERS

### **SECTION 1: OPENING & SMALL TALK**

---

#### **Q1: "Hi! How are you doing today?"**

**Expected Answer:**
"I'm doing great, thank you! I'm excited to talk about this ML Engineer role at Walmart. Thanks for taking the time to speak with me."

**Why This Works:**
✅ Positive energy
✅ Shows enthusiasm
✅ Professional but warm

**Duration:** 20 seconds

---

#### **Q2: "Walk me through your resume briefly"**

**Expected Answer (60-90 seconds):**

"Sure! I'm [Name], I have [X years] of experience in machine learning and data science. 

My background:
- **Education:** [Your degree] from [University] in [Major]
- **Current/Recent Role:** [Title] at [Company] - focus on [key responsibility]
  - I built [specific project], improving [metric] by [X%]
- **Previous Experience:** [Role] at [Company]
  - Worked on [project] using [technologies]
- **Key Skills:** Python, ML libraries (scikit-learn, TensorFlow), SQL, [other relevant skills]
- **Projects:** [2-3 most impressive projects with brief descriptions]

I'm particularly interested in Walmart because of your work in [specific Walmart initiative], and I believe my experience in [relevant area] aligns well with your team's needs."

**Why This Works:**
✅ Concise but comprehensive
✅ Highlights most relevant experience
✅ Shows knowledge of Walmart
✅ Clear narrative flow

**Duration:** 1.5-2 minutes max

**Example (Fill in your details):**
"I'm Arjun, with 1.5 years of ML engineering experience. I graduated from IIT Bombay with a degree in Computer Science. Currently, I'm at [Company] where I led the recommendation system project, increasing user engagement by 23%. Before that, I worked as a data scientist at [Company] where I built a fraud detection model using XGBoost. My key skills are Python, TensorFlow, scikit-learn, and SQL. I'm particularly excited about Walmart because of your innovations in e-commerce recommendation systems, and my experience building recommendation engines aligns perfectly with what you're looking for."

---

### **SECTION 2: EXPERIENCE & BACKGROUND QUESTIONS**

---

#### **Q3: "Tell me about your most recent ML project"**

**Expected Answer (2-3 minutes):**

Structure: Problem → Approach → Solution → Impact

"I worked on a customer churn prediction model at [Company].

**Problem:** We had a 15% monthly churn rate and needed to identify at-risk customers early to offer retention promotions.

**Approach:**
- Analyzed historical customer data (2 years, 50K customers)
- Engineered features: purchase frequency, recency, monetary value, engagement metrics
- Tried multiple models: Logistic Regression, Random Forest, XGBoost
- Selected XGBoost after 5-fold cross-validation showed 78% AUC-ROC

**Implementation:**
- Built data pipeline using Python + SQL for monthly refresh
- Set up model serving with Flask API
- Integrated with CRM system
- Created monitoring dashboard for model performance

**Results:**
- Achieved 78% precision, 72% recall
- Identified top 5% at-risk customers with 82% accuracy
- Led to 12% reduction in churn (saving $2M annually)
- Model is still in production

**What I Learned:**
- Importance of feature engineering for model performance
- Trade-offs between precision and recall in business context
- End-to-end ownership from problem definition to deployment"

**Why This Works:**
✅ Shows full project lifecycle
✅ Quantifies impact
✅ Demonstrates technical skills
✅ Shows business thinking

**Duration:** 2-3 minutes

---

#### **Q4: "What Machine Learning concepts are you most comfortable with?"**

**Expected Answer:**

"I'm strong in several areas:

1. **Supervised Learning:** I have deep experience with regression and classification problems. I've built multiple models using Random Forests, Gradient Boosting (XGBoost, LightGBM), and Neural Networks. I understand how to select models based on data characteristics and requirements.

2. **Feature Engineering:** This is a strength of mine. I've built features using domain knowledge, statistical methods, and automated feature selection. I understand the importance of feature engineering for model performance.

3. **Model Evaluation:** I'm very comfortable with evaluation metrics - I know when to use precision/recall vs AUC-ROC, understand cross-validation strategies, and how to avoid overfitting.

4. **Recommendation Systems:** I've built collaborative filtering systems and content-based recommenders. I understand cold-start problems and A/B testing for recommendations.

5. **SQL & Data Processing:** I'm proficient in complex SQL queries including window functions, CTEs, and working with large datasets efficiently.

I'm also actively learning about transformer models and deep learning applications in NLP and computer vision, as these are areas Walmart likely uses for product recommendations and computer vision applications."

**Why This Works:**
✅ Honest about strengths
✅ Shows depth in multiple areas
✅ Mentions learning mindset
✅ Connects to Walmart's needs

**Duration:** 1.5-2 minutes

---

#### **Q5: "Tell me about a time you had to learn something new quickly"**

**Expected Answer (STAR Format):**

"Sure! At [Company], our team needed to migrate our recommendation model from a batch system to a real-time serving architecture using Apache Kafka and Redis.

**Situation:** We were using a daily batch job that took 4 hours to retrain and update recommendations. But as our user base grew, we needed real-time updates.

**Task:** I volunteered to lead the architecture redesign, even though I had no prior experience with Kafka or Redis.

**Action:** 
- Spent 2 weeks learning Kafka through tutorials and documentation
- Built a POC (proof of concept) with a simple model
- Collaborated with the infra team to understand their architecture
- Designed and implemented the new real-time pipeline
- Wrote comprehensive documentation for the team

**Result:**
- Reduced recommendation latency from 4 hours to <100ms
- Improved user engagement by 8%
- The system is now handling 10K events/second
- I became the go-to person for real-time ML infrastructure on our team

**What I Learned:** I'm comfortable learning new technologies quickly, especially when there's a clear business need. I rely on documentation, hands-on experimentation, and collaboration with experts."

**Why This Works:**
✅ Shows initiative
✅ Demonstrates learning ability
✅ Shows humble but proactive approach
✅ Quantified impact

**Duration:** 1.5-2 minutes

---

#### **Q6: "What was a time when your model or project failed?"**

**Expected Answer (STAR Format - Be Honest!):**

"Yes, I had a challenging experience early in my ML career.

**Situation:** At [Company], I built a churn prediction model that showed 85% accuracy in testing but performed poorly in production (only 62% accuracy).

**Task:** I needed to figure out why and fix it.

**Action:**
- Analyzed the data drift - production data had different distribution than training data
- Realized I had overfit to historical patterns
- Investigated the feature pipeline - found a bug in real-time feature calculation
- Added data quality checks to catch such issues early
- Implemented a monthly retraining schedule
- Added monitoring dashboards for model performance

**Result:**
- Got production accuracy back to 78%
- Prevented similar issues with other models
- Learned the importance of monitoring, not just model accuracy

**Key Takeaway:** This taught me that model development doesn't end at deployment. Production ML is about continuous monitoring, maintenance, and iteration. I now always design models with production realities in mind - data drift, feature quality, and performance monitoring."

**Why This Works:**
✅ Shows humility and growth mindset
✅ Demonstrates problem-solving
✅ Shows learning from mistakes
✅ Relevant to Walmart's scale

**Duration:** 1.5-2 minutes

---

### **SECTION 3: MOTIVATION & WALMART-SPECIFIC QUESTIONS**

---

#### **Q7: "Why are you interested in Walmart?"**

**Expected Answer (1-2 minutes):**

"I'm excited about Walmart for several reasons:

1. **Scale & Impact:** Walmart serves 240 million+ customers weekly across multiple channels - online, stores, marketplace. The scale and complexity of ML problems here is fascinating. Optimizing recommendations by even 1% impacts millions of customers.

2. **Diverse ML Applications:** I'm drawn to roles with diverse technical challenges. Walmart uses ML for:
   - E-commerce recommendations
   - Supply chain optimization
   - Demand forecasting
   - Computer vision in stores
   - Fraud detection
   This breadth excites me because I'll work on different problem types.

3. **Retail Innovation:** Walmart Connect and the retail media platform represent cutting-edge work in digital transformation. I want to be part of innovation in retail.

4. **Technical Excellence:** I've followed Walmart's engineering blog and research papers. Your work on real-time recommendation systems and ML infrastructure shows technical depth.

5. **Business Impact:** I'm not just interested in building accurate models - I want to understand how they impact the business. At Walmart, the connection between ML and business value is very clear: better recommendations = more sales, better forecast = less waste.

6. **Team & Culture:** I value learning from talented engineers. Walmart's size means I'll work with world-class ML practitioners.

Specifically, I'm very interested in this role because [mention the specific team/project if you know it] aligns with my interests in [recommendation systems/supply chain/computer vision, etc.]."

**Why This Works:**
✅ Shows research about Walmart
✅ Demonstrates technical knowledge
✅ Shows business thinking
✅ Specific reasons (not generic)
✅ Enthusiasm is genuine

**Duration:** 1.5-2 minutes

**⚠️ DON'T SAY:**
❌ "I need a job" or "For the salary"
❌ "Walmart is the biggest company I applied to"
❌ Generic company facts without connection to ML role
❌ Criticism of Walmart's current ML approach

---

#### **Q8: "What's your understanding of what this role involves?"**

**Expected Answer (1-1.5 minutes):**

"Based on the job description and my research, this ML Engineer role involves:

**Primary Responsibilities:**
- Developing and deploying ML models for [recommendation/fraud/forecasting - match the job description]
- Working on the full ML lifecycle - problem definition, data collection, feature engineering, modeling, evaluation, and production serving
- Collaborating with data engineers for data pipelines and infrastructure
- Working with product teams to understand business requirements and translate them to ML solutions

**Key Challenges:**
- Scale: Handling data from 240M+ customers
- Real-time serving: Many of Walmart's applications require low-latency recommendations
- A/B testing and experimentation to measure business impact
- Data quality and monitoring in production

**What I'm Prepared For:**
- Learning your tech stack (I'm familiar with Python, SQL, and common ML frameworks)
- Working in a collaborative environment with data engineers, analysts, and product teams
- Balancing technical excellence with business impact
- Taking ownership of problems end-to-end

I'm particularly excited about [specific aspect from job description like 'building real-time recommendation systems' or 'supply chain optimization'] because it aligns with where I want to grow my skills."

**Why This Works:**
✅ Shows you read the job description
✅ Demonstrates understanding of scope
✅ Shows readiness to contribute
✅ Acknowledges team collaboration

**Duration:** 1-1.5 minutes

---

#### **Q9: "How would you approach learning our codebase and tools?"**

**Expected Answer (1 minute):**

"Great question! Here's my approach to onboarding:

1. **Documentation First:** I'd carefully read any internal documentation, architecture docs, and READMEs to understand the system.

2. **Talk to Teammates:** I'd set up meetings with team members who own different parts of the system. Understanding the 'why' behind design decisions is crucial.

3. **Small Tasks First:** I'd volunteer for small, well-scoped tasks to understand the codebase incrementally rather than trying to tackle big projects immediately.

4. **Set Up Local Environment:** I'd ensure I can run code locally, write tests, and understand the development workflow.

5. **Code Review:** I'd carefully review others' code and ask questions to learn best practices.

6. **Documentation:** As I learn, I'd document gaps in existing documentation - this helps both me and future engineers.

7. **Ask Questions:** I'm not shy about asking for clarification. I believe good questions help me learn faster.

Generally, I find that I ramp up quickly on new codebases - in my previous role, I was productive within 2-3 weeks and leading projects within a month. I'm a self-directed learner and proactive about understanding systems."

**Why This Works:**
✅ Shows mature, structured approach
✅ Emphasizes collaboration
✅ Shows initiative (documentation)
✅ Realistic timeline

**Duration:** 1 minute

---

### **SECTION 4: LOGISTICAL QUESTIONS**

---

#### **Q10: "Are you currently employed? If yes, what's your notice period?"**

**Expected Answer:**

**If Employed:**
"Yes, I'm currently at [Company] in the role of [Title]. My notice period is [2 weeks / 1 month / other]. I'm planning to give my notice as soon as I receive an offer from Walmart. I take professional transitions seriously, so I want to ensure a smooth handoff of my responsibilities."

**If Not Employed:**
"I'm currently between roles. I'm immediately available to join and can start on [date]."

**Why This Works:**
✅ Professional tone
✅ Shows consideration for current employer
✅ Clear timeline

**Duration:** 30 seconds

---

#### **Q11: "Are you open to relocation? We have offices in Bentonville, AR and also support remote work."**

**Expected Answer:**

(Choose one that's true for you)

**Option A - Open to Relocation:**
"Yes, I'm open to relocating to Bentonville. I'm interested in being in the same location as the team for collaboration and learning. However, I'd also appreciate learning about any remote work flexibility for certain days if the role supports it."

**Option B - Prefer Remote:**
"I'm very interested in this role and team. My preference would be remote or hybrid if the role supports it, but I'm willing to discuss what works best for the team's needs. I've worked remotely effectively before and maintain strong communication with distributed teams."

**Option C - Flexible:**
"I'm flexible on this. I can relocate to Bentonville if that's what the team needs, or I'm comfortable working remote. I'm happy to discuss what arrangement makes most sense for the role."

**Why This Matters:**
Recruiters need to know logistics. Being open increases your chances, but being honest about preferences is important for long-term satisfaction.

**⚠️ DON'T SAY:**
❌ "I'll do whatever" (seems untrustworthy)
❌ Demanding remote if the role requires onsite
❌ Multiple contradictory statements

**Duration:** 30-45 seconds

---

#### **Q12: "What's your salary expectation?"**

**Expected Answer:**

"Thank you for asking. Based on my research of market rates for ML Engineer roles with my experience level in [location/market], combined with my skills and contributions, I'm expecting a salary in the range of $[X] to $[Y] per year, depending on the role level and total compensation package including bonus and equity.

However, I'm more focused on finding the right role where I can grow and make an impact. I'm flexible and happy to discuss compensation once we've confirmed this is a good fit for both sides."

**IMPORTANT GUIDELINES:**
- Research market rates beforehand using Levels.fyi, Glassdoor, LinkedIn Salary
- Walmart AI/ML Engineer salaries typically:
  - L3 (Junior): $130K-$160K base
  - L4 (Mid): $160K-$200K base
  - L5+ (Senior): $200K+

- Include stock options and bonus (typical: 15-20% bonus, stock grants)
- If unsure, ask: "Can you share the salary range for this level?"
- Never give a number first if possible
- Don't undersell yourself, but be reasonable

**Why This Works:**
✅ Shows research and professionalism
✅ Indicates confidence without arrogance
✅ Stays flexible
✅ Shows priorities are right (role fit over money, but money is important)

**Duration:** 1 minute

---

#### **Q13: "When could you start if we move forward?"**

**Expected Answer:**

"I can start on [specific date - typically 2 weeks to 1 month from now, depending on notice period]. I want to ensure I give appropriate notice to my current employer and wrap up my responsibilities professionally. I'm flexible within reason if your team has a specific start date preference."

**Why This Works:**
✅ Clear timeline
✅ Shows professionalism
✅ Flexible but realistic

**Duration:** 30 seconds

---

#### **Q14: "Do you have any questions about the role, team, or company?"**

**ALWAYS ASK QUESTIONS! This is important!**

**Great Questions to Ask:**

1. **About the Team:**
   - "Can you tell me more about the team I'd be working with? What's the team size and what projects are they currently focused on?"
   - "What's the team structure? Will I be working directly with data engineers and product managers?"

2. **About the Role:**
   - "What are the top 2-3 priorities for this role in the first 6 months?"
   - "What does success look like for this position after 1 year?"
   - "What's the typical project structure - do engineers lead projects end-to-end or work in specific areas?"

3. **About Growth:**
   - "What opportunities are there for learning and career growth in this role?"
   - "Are there opportunities to work on different projects or teams?"

4. **About Onboarding:**
   - "What's the onboarding process like? How long does it typically take to be productive?"
   - "Who would be my primary point of contact during onboarding?"

5. **About the Interview Process:**
   - "What's the timeline for the next steps in the interview process?"
   - "When would you like me to hear back from you?"
   - "What should I prepare for the next round?"

6. **About the Work:**
   - "What's the current ML infrastructure like? What tools and frameworks does the team use?"
   - "How are decisions made about which projects to prioritize?"

**QUESTIONS TO AVOID:**
❌ Questions you could find on Walmart's website
❌ "How much vacation do we get?" (save for later rounds)
❌ Questions about salary/compensation (save for later rounds)
❌ Anything negative or critical
❌ No questions (shows disinterest)

**Why This Matters:**
✅ Shows genuine interest
✅ Helps you evaluate if it's right for you
✅ Demonstrates thoughtfulness
✅ Recruiters expect this

**Duration:** 3-5 minutes

---

## 📊 COMPLETE QUESTION CHECKLIST

Here's what you might get asked:

### Opening & Rapport (2-3 min)
- [ ] "How are you doing today?"
- [ ] "Tell me a bit about yourself"
- [ ] "Walk me through your resume"

### Experience & Technical (8-10 min)
- [ ] "Tell me about your most recent ML project"
- [ ] "What areas of ML are you most comfortable with?"
- [ ] "What's your experience with [specific tech]?"
- [ ] "Tell me about a time you learned something new quickly"
- [ ] "Describe a project where you had to deal with ambiguity"
- [ ] "Tell me about a time your project/model failed"
- [ ] "What's your experience with end-to-end ML projects?"
- [ ] "How do you stay updated on ML trends?"

### Motivation & Fit (5-7 min)
- [ ] "Why are you interested in Walmart?"
- [ ] "What do you know about this role?"
- [ ] "Why are you interested in this specific role/team?"
- [ ] "How would you approach learning our codebase?"
- [ ] "Tell me about your ideal role/team"

### Logistics (3-5 min)
- [ ] "Are you currently employed?"
- [ ] "What's your notice period?"
- [ ] "Are you open to relocation/remote work?"
- [ ] "What's your salary expectation?"
- [ ] "When could you start?"
- [ ] "Do you have any questions?"

---

## ✅ TIPS FOR SUCCESS

### Before the Call
- [ ] Research Walmart thoroughly (company, AI/ML initiatives, recent news)
- [ ] Review job description multiple times
- [ ] Prepare your 2-3 best project stories
- [ ] Practice your resume walk-through (limit to 2 min)
- [ ] Test your internet, microphone, camera
- [ ] Prepare 5-7 questions about the role/team
- [ ] Have resume, notes in front of you
- [ ] Choose a quiet, professional location
- [ ] Set up 5 minutes early

### During the Call
- [ ] Smile - it comes through in your voice
- [ ] Speak clearly and at normal pace
- [ ] Listen fully before answering
- [ ] Don't interrupt
- [ ] Ask for clarification if needed
- [ ] Give specific examples with numbers/impact
- [ ] Show enthusiasm for Walmart
- [ ] Be authentic - don't try to be someone you're not
- [ ] Keep answers focused (1-3 minutes typically)
- [ ] Make strong eye contact if on video

### Answering Strategy
1. **Listen to full question**
2. **Take 2-3 seconds to think**
3. **Give focused answer** with specific examples
4. **Add one learning or insight**
5. **Brief pause** - let interviewer ask follow-up or move on

### Story Structure (STAR Method)
- **S**ituation - Context
- **T**ask - Your responsibility
- **A**ction - What YOU did (emphasize your role)
- **R**esult - Quantifiable outcome + learning

---

## ❌ COMMON MISTAKES TO AVOID

| Mistake | Why It's Bad | Solution |
|---------|------------|----------|
| **Rambling stories** | Loses interviewer's attention | Practice keeping stories to 2-3 min |
| **Vague answers** | Shows lack of clarity/depth | Use specific examples with numbers |
| **Saying "I don't know"** | Without effort | Say "That's a great question, I don't have experience with that, but I'd be eager to learn..." |
| **Criticizing past employers** | Major red flag | Focus on what you learned |
| **Not asking questions** | Seems disinterested | Ask 3-5 thoughtful questions |
| **Saying you'll "do anything"** | Seems desperate | Be honest about preferences |
| **Not knowing about Walmart** | Shows lack of research | Do 30 min of research before call |
| **Excessive "ums" and "ahs"** | Affects credibility | Pause instead of filler words |
| **Contradicting yourself** | Undermines credibility | Be consistent in stories and details |
| **Getting defensive** | Negative impression | Stay positive and reflective |

---

## 🎬 SAMPLE CALL TRANSCRIPT

**Recruiter:** "Hi Arjun! Thanks for taking the time to speak with me today. How are you doing?"

**You:** "Great! Thanks for having me. I'm excited to learn more about this ML Engineer role at Walmart."

**Recruiter:** "Awesome! Let me tell you a bit about the role, and then I'd love to hear about your background. We're looking for an ML Engineer to work on our recommendation systems serving 240M+ weekly customers. The role involves building scalable ML pipelines, working with real-time data, and collaborating with data engineers and product teams. Does this sound interesting?"

**You:** "Absolutely! That's exactly the kind of work I'm looking for. I've built recommendation systems at [Company], so I understand the complexity of personalization at scale. I'm very interested in learning more."

**Recruiter:** "Great! Walk me through your background briefly."

**You:** "Sure! I'm Arjun, with 1.5 years of ML engineering experience. I graduated from IIT Bombay with a CS degree. Currently at [Company], I led the recommendation system project, increasing user engagement by 23%. Before that, I was a data scientist at [Company] where I built fraud detection models using XGBoost. My key skills are Python, TensorFlow, scikit-learn, and SQL. I'm particularly excited about Walmart because of your innovations in e-commerce and the scale of problems you solve. Could you tell me more about the specific team I'd be working with?"

**Recruiter:** "Happy to! Tell me about your most recent project and how it impacted the business."

**You:** "[Give STAR story - 2-3 minutes with specific metrics]"

**Recruiter:** "That's great! Do you have any experience with [specific technology]?"

**You:** "[Answer with experience or willingness to learn]"

**Recruiter:** "Last few logistics - are you open to relocation to Bentonville or prefer remote?"

**You:** "I'm flexible. I'd prefer to discuss what works best for the team, but I'm open to both options."

**Recruiter:** "What's your salary expectation?"

**You:** "Based on my research and my experience, I'm expecting $150-170K base salary depending on level and total comp package. I'm flexible and would like to understand the full package."

**Recruiter:** "Do you have any questions for me?"

**You:** "Yes! Could you tell me about the team composition and the top priorities for this role in the first 6 months?"

[Continue with your prepared questions]

---

## 🎯 WHAT RECRUITERS ARE REALLY ASSESSING

✅ **Communication Skills**
- Can you explain complex ideas clearly?
- Do you listen well?

✅ **Technical Credibility**
- Do you have relevant ML experience?
- Can you discuss projects with depth?

✅ **Enthusiasm for Walmart**
- Did you research the company?
- Do you understand the role?

✅ **Professionalism**
- Are you articulate and courteous?
- Will you be a good colleague?

✅ **Alignment**
- Does this role match your goals?
- Will you stay long-term?

✅ **Coachability**
- Are you willing to learn?
- Do you accept feedback?

---

## 📋 FINAL CHECKLIST BEFORE YOUR CALL

**72 Hours Before:**
- [ ] Research Walmart AI/ML initiatives
- [ ] Read job description 3 times
- [ ] Prepare 2-3 project stories (with metrics)
- [ ] Write down 5-7 questions
- [ ] Research market salary

**24 Hours Before:**
- [ ] Practice talking through your resume (time it - should be 2 min)
- [ ] Practice your project stories
- [ ] Test your tech setup (video, audio, internet)
- [ ] Check what you'll wear
- [ ] Get good sleep

**1 Hour Before:**
- [ ] Take a walk or do breathing exercises
- [ ] Find your quiet location
- [ ] Have water ready
- [ ] Open your notes discreetly on a tab
- [ ] Clear any distractions (notifications, etc.)

**5 Minutes Before:**
- [ ] Join call early
- [ ] Smile and take deep breath
- [ ] Positive mindset - you've got this!

---

## 🎓 FINAL THOUGHTS

**The recruiter screen is NOT about testing your technical knowledge deeply.** It's about:
✅ Communication
✅ Enthusiasm  
✅ Basic fit for the role
✅ Professionalism
✅ No red flags

If you:
- Communicate clearly
- Show genuine interest in Walmart
- Have relevant experience
- Ask thoughtful questions
- Are professional

**You'll pass this round ~80% of the time!**

The hard rounds are 2-4 (coding and system design). Round 1 is your warm-up!

---

## 💪 YOU'VE GOT THIS!

Go into this call confident knowing you've prepared thoroughly. The recruiter wants to like you - you just need to give them reasons to!

**Good luck! 🚀**
