# CodeLeela Requirements Document

## Introduction

CodeLeela is an innovative educational platform with the tagline "Learn code through stories - programming made simple for Bharat." The platform transforms programming concepts into engaging, culturally relevant stories that make coding accessible to absolute beginners across India. By using Indian cultural metaphors, trilingual support (Hindi, English, Gujarati), and visual storytelling, CodeLeela addresses the critical gap in programming education for India's diverse learners.

## Project Vision

**Target Users:**
- Absolute beginners (students from school/college )
- Professionals with non-CS backgrounds
- students from tier 2/3 cities
- Hindi/Gujarati speaking learners
- Educators and NGOs
- Self-learners seeking intuitive programming education

**Core Problems Addressed:**
- Language Barrier: 100M+ Indians want to learn programming, but most resources are English-only
- Learning Approach Gap: Traditional tutorials are syntax-focused rather than concept-focused, leading to high dropout rates
- Complex Topics: Existing platforms show code but don't build intuition; visual learning resources are scarce

## Glossary

- **CodeLeela**: The complete educational platform for story-based programming learning
- **Story_Engine**: Component responsible for converting code logic into narrative elements using Indian cultural metaphors
- **Visual_Renderer**: Component that creates visual representations using metaphors like trains for linked lists, cricket teams for arrays
- **Narration_System**: Component handling trilingual audio explanations (Hindi, English, Gujarati)
- **Code_Parser**: Component that analyzes code structure for basic topics (arrays, variables, loops, data types) to advanced DSA topics (stacks, linked lists, recursion)
- **Metaphor_Mapper**: Component that maps technical concepts to Indian cultural metaphors (cricket, chai stalls, trains, pots storing water)
- **User_Interface**: Streamlit-based interactive interface for code input and story visualization
- **AWS_Bedrock**: Amazon's AI service (Claude Sonnet 4) for intelligent story generation and code analysis
- **AWS_Polly**: Amazon's text-to-speech service for trilingual narration (Aditi for Hindi/Gujarati, Joanna/Matthew for English)

## Requirements

### Requirement 1: Code Analysis and Parsing for Educational Topics

**User Story:** As a beginner learner, I want to input code covering basic to intermediate programming concepts, so that the system can analyze and explain topics from variables and arrays to data structures like stacks and linked lists through stories.

#### Acceptance Criteria

1. WHEN a user inputs code with basic concepts (variables, arrays, loops, data types), THE Code_Parser SHALL analyze the structure and identify educational opportunities for story generation
2. WHEN parsing intermediate concepts (functions, conditionals, basic algorithms), THE Code_Parser SHALL extract logical relationships and execution flow for narrative mapping
3. WHEN processing advanced DSA topics (stacks, linked lists, recursion, trees), THE Code_Parser SHALL maintain hierarchical relationships and algorithmic patterns for complex story generation
4. WHEN invalid code is provided, THE Code_Parser SHALL return beginner-friendly error messages in the user's preferred language (Hindi/English/Gujarati) with learning suggestions

### Requirement 2: AI-Powered Story Generation with Indian Cultural Context

**User Story:** As a learner from India, I want programming concepts explained through familiar cultural references and stories, so that I can understand code logic through relatable Indian metaphors and contexts.

#### Acceptance Criteria

1. WHEN parsed code is processed, THE Story_Engine SHALL use AWS Bedrock (Claude Sonnet 4) to generate stories using Indian cultural metaphors like cricket teams for arrays, train compartments for linked lists, and chai stalls for variables
2. WHEN generating stories, THE Story_Engine SHALL incorporate context-appropriate Indian cultural references (festivals, mythology, family structures, daily life scenarios) that match the programming concept being taught
3. WHEN creating narratives, THE Story_Engine SHALL build intuition before introducing syntax, making learning engaging and memorable through story-first approach
4. WHEN story generation encounters unfamiliar concepts, THE Story_Engine SHALL provide culturally neutral metaphors while maintaining educational value and logging for future cultural mapping improvements

### Requirement 3: Visual Metaphor System

**User Story:** As a visual learner, I want to see programming concepts represented through familiar visual metaphors, so that I can understand abstract programming concepts through concrete, relatable imagery.

#### Acceptance Criteria

1. WHEN displaying data structures, THE Visual_Renderer SHALL use specific Indian metaphors: linked lists as train compartments, arrays as cricket team lineups, variables as pots storing water, stacks as plate arrangements
2. WHEN rendering algorithms and logic flow, THE Visual_Renderer SHALL create visual narratives showing data movement, transformations, and relationships through animated metaphorical representations
3. WHEN presenting complex programming concepts, THE Visual_Renderer SHALL use hybrid visual generation combining pre-made library assets with AI-generated visuals from Pollinations.ai or Segmind when needed
4. WHEN visual generation fails, THE Visual_Renderer SHALL display pre-made placeholder visuals from the library while maintaining story continuity and educational value

### Requirement 4: Trilingual Narration System

**User Story:** As a learner who is more comfortable with Hindi or Gujarati, I want to hear explanations in my preferred language, so that I can learn programming concepts without language barriers.

#### Acceptance Criteria

1. WHEN story content is ready, THE Narration_System SHALL generate trilingual text explanations (Hindi, English, Gujarati) for each story segment with culturally appropriate context
2. WHEN creating audio, THE Narration_System SHALL use AWS Polly with Aditi voice for Hindi and Gujarati, and Joanna/Matthew voices for English to produce high-quality speech
3. WHEN switching between languages, THE Narration_System SHALL maintain story coherence, cultural context appropriateness, and preserve the educational value across all three languages
4. WHEN audio generation fails, THE Narration_System SHALL provide text-only explanations in the selected language while attempting audio regeneration in the background

### Requirement 5: Streamlit-Based Interactive Learning Experience

**User Story:** As a beginner learner, I want an intuitive, web-based interface where I can easily input code and interact with the generated stories, so that I can learn at my own pace without technical complexity.

#### Acceptance Criteria

1. WHEN using the platform, THE User_Interface SHALL provide a Streamlit-based web interface with built-in components for rapid prototyping and easy deployment without requiring JavaScript knowledge
2. WHEN interacting with stories, THE User_Interface SHALL provide intuitive controls to pause, replay, navigate through story segments, and switch between the three supported languages
3. WHEN exploring learning content, THE User_Interface SHALL allow users to toggle between story view and actual code view, with detailed explanations of code-to-story mappings
4. WHEN user interactions occur, THE User_Interface SHALL maintain responsive feedback, smooth transitions, and provide contextual help for absolute beginners

### Requirement 6: Comprehensive Indian Cultural Metaphor Integration

**User Story:** As a learner from diverse Indian cultural backgrounds, I want programming concepts explained through familiar cultural references from my daily life, so that learning feels natural, relatable, and culturally appropriate.

#### Acceptance Criteria

1. WHEN mapping programming concepts, THE Metaphor_Mapper SHALL use diverse Indian cultural elements including festivals (Diwali, Holi), mythology (Ramayana, Mahabharata), family structures (joint families, relationships), and daily life scenarios (markets, transportation, food preparation)
2. WHEN creating character representations, THE Metaphor_Mapper SHALL incorporate culturally appropriate visual designs, naming conventions, and behavioral patterns that resonate with Indian learners
3. WHEN explaining programming patterns, THE Metaphor_Mapper SHALL draw parallels to familiar cultural practices like organizing festivals, managing household tasks, or traditional games and sports
4. WHEN specific cultural mappings are unavailable, THE Metaphor_Mapper SHALL use universal metaphors while maintaining cultural sensitivity and logging gaps for future enhancement

### Requirement 7: Educational Accessibility for Absolute Beginners

**User Story:** As an absolute beginner with no programming background, I want the system to explain concepts in simple, everyday language without technical jargon, so that I can build programming intuition gradually and confidently.

#### Acceptance Criteria

1. WHEN generating explanations, THE System SHALL avoid technical programming terminology and use everyday language appropriate for school/college students and non-CS professionals
2. WHEN presenting complex concepts, THE System SHALL break them down into simple, progressive story elements that build from basic understanding to more advanced concepts
3. WHEN users encounter learning difficulties, THE System SHALL provide scaffolded learning with progressive disclosure from basics to advanced topics, including contextual hints and learning tips
4. WHEN educational content is displayed, THE System SHALL include beginner-friendly explanations, visual cues, and encourage exploration without fear of making mistakes

### Requirement 8: AWS Service Integration with Fallback Support

**User Story:** As a platform user, I want reliable access to AI-powered story generation and voice narration, so that my learning experience remains consistent even when cloud services face issues.

#### Acceptance Criteria

1. WHEN connecting to AWS Bedrock (Claude Sonnet 4), THE System SHALL authenticate securely, handle API rate limits appropriately, and manage code analysis, metaphor generation, story creation, and explanation generation efficiently
2. WHEN using AWS Polly for trilingual narration, THE System SHALL manage voice selection (Aditi for Hindi/Gujarati, Joanna/Matthew for English), speech rate, and audio quality settings for optimal learning experience
3. WHEN AWS services are unavailable, THE System SHALL implement graceful degradation with local fallback capabilities including pre-generated story templates and text-only explanations
4. WHEN API errors occur, THE System SHALL log errors appropriately, provide user-friendly error messages in the user's preferred language, and attempt automatic recovery

### Requirement 9: Performance and Responsiveness for Diverse Users

**User Story:** As a learner potentially using the platform on slower internet connections or devices, I want the system to process my code and generate stories quickly, so that my learning experience remains engaging regardless of my technical setup.

#### Acceptance Criteria

1. WHEN processing code covering basic to DSA topics, THE System SHALL complete analysis and initial story generation within 10 seconds for typical code snippets, optimizing for users in tier 2/3 cities with varying internet speeds
2. WHEN rendering visual metaphors and animations, THE System SHALL maintain smooth performance using Streamlit's built-in components and Pillow for image processing, ensuring accessibility across different devices
3. WHEN generating trilingual audio narration, THE System SHALL stream narration efficiently to minimize waiting time and provide progressive loading for better user experience
4. WHEN system load is high, THE System SHALL prioritize user interactions, provide clear loading indicators, and maintain responsive feedback for educational continuity

### Requirement 10: Content Quality and Educational Effectiveness

**User Story:** As an educator or NGO using this platform, I want the generated stories to be pedagogically sound, culturally appropriate, and educationally effective, so that students receive accurate and helpful programming education that builds real understanding.

#### Acceptance Criteria

1. WHEN generating stories for any programming concept, THE System SHALL ensure narrative accuracy reflects actual code behavior and logic, maintaining educational integrity from basic variables to complex DSA topics
2. WHEN creating educational content across topics, THE System SHALL maintain consistent metaphor usage (trains for linked lists, cricket teams for arrays) and ensure progressive learning paths from basics to advanced concepts
3. WHEN producing trilingual content, THE System SHALL ensure translation accuracy, cultural appropriateness across Hindi, English, and Gujarati, and preserve educational value in all languages
4. WHEN content quality issues are detected, THE System SHALL flag content for review, provide alternative explanations, and continuously improve the cultural metaphor database based on user feedback and educational outcomes