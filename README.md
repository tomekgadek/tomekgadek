## Hi there 👋

```java
/* --- resume --- */

import java.time.LocalDate;
import java.util.List;
import java.util.stream.Collectors;

enum Language { POLISH, ENGLISH }
enum LanguageLevel { NATIVE, INTERMEDIATE }
enum Job { PROGRAMMER, TEACHER, AUTHOR, GIS_OPERATOR }

record Education(String begin, String end, String schoolName) {}
record WorkExperience(String begin, String end, Job position, String companyName) {}
record KnownLanguage(Language language, LanguageLevel level) {}

public class Resume {
    private final String name = "Tomasz Gadek";
    private final LocalDate birthday = LocalDate.of(1987, 7, 17);
    private final String email = "gadektomek@gmail.com";
    private final String drivingLicense = "B";
    private final String interests = "DANCE";
    private final String certificates = "TDD | WORK WITH LEGACY CODE | CLEAN CODE";
    
    private final List<Education> educationList;
    private final List<WorkExperience> workExperienceList;
    private final List<KnownLanguage> knownLanguages;

    public Resume() {
        educationList = List.of(
            new Education("2011", "2013", "Jagiellonian University"),
            new Education("2007", "2011", "Collegium Tarnoviense")
        );

        workExperienceList = List.of(
            new WorkExperience("2020", "...", Job.AUTHOR, "THE HERO"),
            new WorkExperience("2020", "...", Job.PROGRAMMER, "THE HERO"),
            new WorkExperience("2017", "...", Job.TEACHER, "COLLEGIUM TARNOVIENSE"),
            new WorkExperience("2019", "2020", Job.PROGRAMMER, "HCM DECK"),
            new WorkExperience("2014", "2019", Job.PROGRAMMER, "ALTCONNECT"),
            new WorkExperience("2011", "2013", Job.GIS_OPERATOR, "MGGP AERO")
        );

        knownLanguages = List.of(
            new KnownLanguage(Language.POLISH, LanguageLevel.NATIVE),
            new KnownLanguage(Language.ENGLISH, LanguageLevel.INTERMEDIATE)
        );
    }

    @Override
    public String toString() {
        return String.join("\n",
            "Name: " + name,
            "Birthday: " + birthday,
            "Email: " + email,
            "",
            "Education:",
            educationList.stream()
                .map(e -> e.begin() + " - " + e.end() + ": " + e.schoolName())
                .collect(Collectors.joining("\n")),
            "",
            "Work Experience:",
            workExperienceList.stream()
                .map(w -> w.begin() + " - " + w.end() + ": " + w.position() + " at " + w.companyName())
                .collect(Collectors.joining("\n")),
            "",
            "Languages:",
            knownLanguages.stream()
                .map(l -> l.language() + ": " + l.level())
                .collect(Collectors.joining("\n")),
            "",
            "Driving License: " + drivingLicense,
            "Interests: " + interests,
            "Certificates: " + certificates
        );
    }

    public static void main(String[] args) {
        var resume = new Resume();
        System.out.println(resume);
    }
}

/* --- resume --- */
```

<!--
**tomekgadek/tomekgadek** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
