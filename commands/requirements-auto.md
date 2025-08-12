# Auto Requirements Gathering

Automatically gather complete requirements for a feature using all defaults.

Takes: $ARGUMENTS (feature description)

## Instructions:

### Step 1: Start Requirements Process
1. Run requirements-start with the provided feature description from $ARGUMENTS
2. This will create the requirement folder and initial setup

### Step 2: Auto-Answer Discovery Phase
3. Read the current requirement status to see what questions need answering
4. For each discovery question in 01-discovery-questions.md:
   - Read the question and its default answer
   - Automatically respond with the suggested default
   - Update progress after each answer
   - Continue until all 5 discovery questions are answered

### Step 3: Wait for Context Gathering 
5. Let the system complete autonomous context gathering phase
6. Wait for detail questions to be generated

### Step 4: Auto-Answer Detail Phase
7. For each detail question in 04-detail-questions.md:
   - Read the question and its default answer
   - Automatically respond with the suggested default
   - Update progress after each answer
   - Continue until all detail questions are answered

### Step 5: Complete Process
8. Ensure final requirements spec (06-requirements-spec.md) is generated
9. Mark requirement as complete
10. Show summary of what was created

## Auto-Answer Logic:
- Always use the "Default if unknown" value provided in each question
- If default says "Yes" → respond "YES" 
- If default says "No" → respond "NO"
- If unclear → respond "IDK" and let system decide

## Error Handling:
- If requirements-start fails, stop and report error
- If questions file doesn't exist, wait and retry
- If no default provided in question, respond "IDK"

## Success Criteria:
- ✅ Requirements started successfully
- ✅ All discovery questions answered with defaults
- ✅ Context gathering completed
- ✅ All detail questions answered with defaults  
- ✅ Final requirements spec generated
- ✅ Process marked as complete

## Output Format:
```
🎯 Feature: [feature description from $ARGUMENTS]
📋 Starting automated requirements gathering...

✅ Phase 1: Requirements started
✅ Phase 2: Discovery questions (5/5 answered with defaults)
✅ Phase 3: Context gathering completed
✅ Phase 4: Detail questions (X/X answered with defaults)
✅ Phase 5: Requirements spec generated

📁 Generated files:
- requirements/[folder]/06-requirements-spec.md
- [other files]

🚀 Ready for implementation!
```

This command fully automates the requirements gathering pipeline using smart defaults!