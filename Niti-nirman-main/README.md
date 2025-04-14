
# Project Title

NitiNirman: AI-Powered Platform for Simplified Access to Government Schemes



NitiNirman is an AI-driven platform designed to empower citizens, especially those in rural areas, by streamlining access to government schemes and services. The platform leverages advanced technologies like AI, blockchain, and API integrations to improve accessibility, efficiency, and user experience. Key features include tailored scheme recommendations based on user profiles, document verification via government APIs, blockchain-secured document storage, and a chatbot for essential scheme information. With a user-centric design, NitiNirman aims to bridge the gap between citizens and government resources, ensuring inclusivity and transparency.

Team: Ayush kakkar, Shreya Kumari 
## Deployment

To run this project locally

```bash
  npm run start
```

Create a .env file in root directory with

```bash
VITE_SUPABASE_URL=
VITE_SUPABASE_ANON_KEY=
VITE_GEMINI_API_KEY= 
VITE_SYSTEM_PROMPT= (system prompt for chatbot)
```

- Create tables in supabase 

First create this Enum types

```bash
-- Create gender type enum
CREATE TYPE public.gender_type AS ENUM (
    'male',
    'female',
    'other'
);

-- Create location type enum
CREATE TYPE public.location_type AS ENUM (
    'rural',
    'urban'
);

-- Create yes_no_anyone type enum
CREATE TYPE public.yes_no_anyone AS ENUM (
    'yes',
    'no',
    'anyone'
);
```

1. user_profiles 

``` bash
-- Create user_profiles table in the public schema
CREATE TABLE public.user_profiles (
    id UUID NOT NULL DEFAULT extensions.uuid_generate_v4(),
    email CHARACTER VARYING NOT NULL,
    gender public.gender_type NOT NULL,
    age INTEGER NOT NULL,
    location public.location_type NOT NULL,
    caste CHARACTER VARYING NOT NULL,
    disability public.yes_no_anyone NOT NULL,
    minority public.yes_no_anyone NOT NULL,
    student public.yes_no_anyone NOT NULL,
    bpl public.yes_no_anyone NOT NULL,
    income NUMERIC NOT NULL,
    pincode TEXT NULL,
    state CHARACTER VARYING(100) NULL,
    city CHARACTER VARYING(100) NULL,
    aadhar_verified BOOLEAN NULL DEFAULT false,
    name CHARACTER VARYING(100) NULL,
    profile_photo TEXT NULL,
) TABLESPACE pg_default;

```

## Support

For support or any queries, email shreyaaasingh8@gmail.com



    
