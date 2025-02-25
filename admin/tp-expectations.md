{% from "common/macros.njk" import embed_topic with context %}
{% from "common/admin.njk" import show_admin_page with context %}

{% call show_admin_page("tp-expectations") %}
<div id="main">

<span class="keyword d-none">project expectations</span>

<!-- ==================================================================================================== -->

## Outcomes

The high-level learning outcome of the team project (tP):

<box> {{ icon_outcome }} Can contribute production quality SE work to a small/medium {{ "_brownfield_ " if cs2103 or tic4002 }}software project </box>

<div tags="m--cs2103 m--tic4002">

Accordingly, the tP is structured to resemble an intermediate stage of a non-trivial real-life brownfield software project in which you will,
 1. conceptualize and implement enhancements to a given product, and,
 1. have it ready to be continued by future developers
</div>
<div tags="m--cs2113 m--tic4001">

Accordingly, the tP is structured to resemble an early stage of a small software project in which you will,
 1. conceptualize and implement a product, and,
 1. have it ready to be continued by future developers
</div>

The focus of the tP is to learn the following aspects:
1. ~~coding~~ %%(taken for granted, not focused on specifically)%%
1. working in a team
1. process/workflow
1. documentation
1. scheduling and tracking project progress, meeting delivery deadline
1. quality assurance

<box type="info" tags="m--tic4002" icon=":fas-not-equal:" seamless>

**TIC4001 vs TIC4002**{.text-info}

TIC4002 focuses on aspect 6 in particular, as TIC4001 already covered 2-5 above (but you should improve on the 2-5 in this module as well).
</box>

<span id="tp-direction">

<!-- ==================================================================================================== -->

## Direction

<div tags="m--cs2103 m--tic4002">

The tP uses a generic application called [AddressBook-Level3 (AB3)](https://se-edu.github.io/addressbook-level3/) (from https://se-education.org) as the starting point.

<img src="https://github.com/se-edu/addressbook-level3/raw/master/docs/images/Ui.png" width="600"/>
<p/>

</div>

You may develop any product provided it is meant for users who can type fast, and prefer typing over mouse/voice commands. Therefore, ==Command Line Interface (CLI) is the primary mode of input.==

{{ embed_topic("tp-constraints.md#Constraint-Typing-Preferred", "Admin " + icon_embedding + " tP Contstraints → Constraint-Typing-Preferred", "2", indent="1") }}
{{ embed_topic("tp-constraints.md#Recommendation-CLI-First", "Admin " + icon_embedding + " tP Contstraints → Recommendation-CLI-First", "2", indent="1") }}
<p/>

{% set morph_examples %}
  For example, an app to manage one of these:{% if module == "CS2113" or module == "TIC4001" %}
    * Contact details{% endif %}
    * Bookmarks of websites
    * Tasks/Schedule
    * Location info
    * Thing to memorize i.e. flash cards, trivia
    * Forum posts, news feeds, Social media feeds
    * Online projects or issue trackers that the user is interested in
    * Emails, possibly from different accounts
    * Multiple types of related things %%e.g. Contacts and Tasks (if Tasks are allocated to Contacts)%%
    * ...
{% endset %}

<span tags="m--cs2103 m--tic4002">

* **Direction 1: Evolve** <tooltip content="AddressBook-Level3">AB3</tooltip> into a more powerful or more optimized contact management app.
  * Some examples:
    * Manage more entity types related to contacts %%e.g. Tasks allocated to contacts%%
    * Contact managing optimized for a specific type of user %%e.g. a sales person managing client contacts%%
    * Make existing features _really_ strong, worthy of a real product %%e.g., make the commands more natural, make the search feature more powerful, tweak the GUI to be more useful, ...%%

<div class="indented-level2">

* {{ pros }} less changes to existing code at the start of the project (i.e., progress will be smoother at the start), can result in a more mature product with deeper features as the product functionality will be moving forward from the start
* {{ cons }} less flexibility in product design.
</div>

* **Direction 2: Morph** AB3 any direction you wish.
  * {{ morph_examples | trim }}

<div class="indented-level2">

* {{ pros }} more flexibility in the project direction
* {{ cons }} more changes to the existing code at the start while you are still not very familiar with the code base, morphing is less common in real projects (compared to direction 1)
</div>

Weigh the pros/cons and choose the one that suits you. Note that ==**creating a novel/unique/interesting product will NOT earn you extra marks**== in this module. While those qualities are important in real world projects, and we do allow you room to go in those directions in this module, they are not the focus of this module {% if cs2103 %}%%(there are other modules such as CS3216, CS3217 that focus on those aspects)%%. Focus your energy on creating a _solid product at a high quality level_, which actually take a lot more energy than you might realize at first. Go for novelty/uniqueness/interesting etc. only if you have energy to spare and can do so without compromising the quality. For example, a bland feature/product implemented well will score more marks than a novel product that is buggy, even if the novel features were harder to implement.

**Our recommendation:**{.text-success} Go with direction 1 unless you have a strong inclination to create a _different_ product. Direction 1 fits both weak and strong programmers, smoother at the start, the risk of schedule overruns is lower (because it can be done in smaller increments all the way, while morphing requires some big changes at the start), and gives you a better chance of reaching a product that is worthy of actual users (as you will not be slowed down by the morphing).
{% endif %}
<div tags="m--cs2113 m--tic4001">

* {{ morph_examples | trim }}
</div>
</span>

<div tags="m--cs2113 m--tic4001">

==You are strongly discouraged from developing a GUI application== as it can increase the workload unnecessarily.
{{ embed_topic("tp-constraints.md#Recommendation-No-GUI", "Admin " + icon_embedding + " tP Contstraints → Recommendation-No-GUI", "2", indent="1") }}
</div>

<box type="info" tags="m--tic4002" seamless>

**You are allowed to reuse the project idea/code from TIC4001**, as long as it fits the TIC4002 requirements/constraints.
</box>

<!-- ==================================================================================================== -->

## Target User & Value Proposition

You are expected to:
* **Define a very specific _target user profile_.** <br> ==We require you to narrow down the target user profile==  %%as opposed to trying to make it as general as possible. Here is an example direction of narrowing down target user: anybody → teachers → university teachers → tech savvy university teachers → {{ module_pair }} instructors.%%<br><br>
 {{ icon_important_big_red }} Be careful not to contradict given [project constraints]({{ baseUrl }}/admin/tp-constraints.html) when defining the user profile %%e.g. the target user should still prefer typing over mouse actions%%.

<div class="indented-level2">

<panel type="seamless" header="%%Why the need to narrow down the user profile?%%" >

* It is an opportunity to exercise your product design skills because optimizing the product to a very specific target user requires good product design skills.
* It minimizes the overlap between features of different teams which can cause plagiarism issues. Furthermore, higher the number of other teams having the same features, less impressive your work becomes especially if others have done a better job of implementing that feature.
</panel>

<panel type="seamless" header="%%How narrow can we make the target market?%%" >

The size of the target market is not a grading criterion. You can make it as narrow as you want. Even a single user target market is fine as long as you can define that single user in a way others can understand (reason: project evaluators need to evaluate the project from the point of view of the target users).
</panel>
</div>

* **Define a clear _value proposition_** that matches the target user profile i.e., what problem does the product solve? how does it make the user's life easier?<br>
  You should also define the _scope_ clearly i.e., boundary beyond which the app will not help %%e.g., the app will help to manage tasks within a single project only (no support for multiple projects)%%.
* **Optimize the product to the chosen target users** i.e., add features that are especially/only applicable for target users (to make the app especially attractive to them). 
  * Example 1: If the product targets {{ module_pair }} instructors, there can be features that are applicable to them only, %%such as the ability to see a link to a student's project on GitHub%%
  * Example 2: If your app manages contacts, you can optimize its features based on,
    * the profession of the target user %%e.g. doctors, salesmen, teachers, etc.%%
    * the nature/scale of contacts %%e.g. huge number of contacts (for HR admins, user group admins), mostly incomplete contacts, highly volatile contact details, contacts become inactive after a specific period (e.g. contract employees)%%
    * what users do with the contacts %%e.g. organize group events, share info, do business, do analytics%%

    {{ icon_tip }} Your project will be graded based on how well the features match the target user profile and how well the features fit-together.

<span id="functionalityExpectations">

<!-- ==================================================================================================== -->

<h2 class="text-white bg-danger p-1">Functionality Expectations</h2>

<div tags="m--cs2103 m--tic4002">

**The expected level of _functionality_ to be added by a 5-person team is roughly the ==equivalent effort taken to create AB3 _functionality_==**. Furthermore, we expect a team to reach that level **if each member puts in an effort equivalent to the effort they put into the iP**. %%So, if the question is "If our team do x, y, and z, is that enough?", the answer is "Yes, if it requires each member to put in about an iP worth of effort".%% Some examples likely to meet that criterion:
* Example 1: A fictional contact management app optimized for a specific target user group:
  * Existing AB3 features are optimized to the new target user group.
  * Person objects are enhanced to contain more details.
  * There are a 4-5 new functionality that are specific to the target user group.
* Example 2: a FooBar app that keeps track of two different types of entities _Foo_ entities and _Bar_ entities.
  * Foo and Bar entities are tightly-connected e.g., a Foo entity can contain Bar entities. Each type is similar to AB3 Person objects in terms of complexity.
  * In addition to <tooltip content="Creat Read Update Delete">CRUD</tooltip> for Foo and Bar entities, there are a 4-5 FooBar-specific functionality, some of which involves both Foo and Bar entities e.g., link a Foo entity to a Bar entity.
</div>
<div tags="m--cs2113 m--tic4001">

**The expected level of _functionality_ from a team is roughly ==what you can achieve if each member contributes about the same amount of functional code as required by a <tooltip content="i.e., if all requirements were met at the _minimal_ level specified">typical iP</tooltip>==**.
</div>

==You will get full marks for implementation effort== if you meet the expectation stated above. There are no extra marks for exceeding that bar. You are better off spending that effort in improving other aspects of the project. Try to avoid adding more features than necessary, unless you are doing it out of interest. As mentioned elsewhere, a functionality just the right size and of high quality will earn more marks than a functionality that is bigger (or more difficult, or more interesting/novel) but of lower quality.


<box type="important" tags="m--cs2103 m--cs2113" seamless>

<div tags="m--cs2103 m--cs2113">

In the most recent semester, more than 80% of the students did significantly more work than what was needed to earn full marks for effort. Many of them were likely under the wrong impression that doing more features will earn them more marks. Try to avoid doing the same mistake yourself.

</div>
<div tags="m--cs2113">

In fact, here is the grading criterion for the individual project effort:
{{ embed_topic("tp-pe.mbdf#projectGrading-effort-instructions", "Admin " + icon_embedding + " tP → PE → ==Evaluating the  Implementation Effort==", "3") }}
</div>
</box>

<box tags="m--cs2103 m--tic4002">

{{ icon_tip }} If you wish to add the following features to your app, we recommend (but not require) you to follow similar features in AB4 in order to reduce the effort required.
  * [Undo/redo](https://se-education.org/addressbook-level4/DeveloperGuide.html#undo-redo-feature)
  * [Automated GUI tests](https://se-education.org/addressbook-level4/Testing.html#types-of-tests)
</box>

</span>
<span id="teamExpectations">

<!-- ==================================================================================================== -->

<h2 class="text-white bg-success p-1">{{ icon_team }} Team Expectations</h2>

* <span class="badge badge-success">Expectation</span> <span class="text-success">**Preserve _product integrity_**</span> i.e. ensure,
  1. features fit together to form a cohesive product,
  1. documentation follows a consistent style and presents a cohesive picture to the reader, and
  1. final project demo presents a cohesive picture to the audience.
* <span class="badge badge-success">Expectation</span> <span class="text-success">**Maintain product quality**</span> i.e. prevent breaking other parts of the product as it evolves. <span tags="m--cs2103 m--tic4002 m--cs2113">Note that bugs local to a specific feature will be counted against the author of that feature. However, if a new enhancement breaks the entire product, the whole team will have to share the penalty.
* <span class="badge badge-success">Expectation</span> <span class="text-success">**Manage the project**</span> i.e. ensure workflow, code maintenance, integration, releases, etc. are done smoothly.
</span>

</span>
<span id="individualExpectations">

<!-- ==================================================================================================== -->

<h2 class="text-white bg-info p-1">{{ icon_individual }} Individual Expectations</h2>

#### <span class="badge badge-info">{{ icon_individual }} Individual</span> <span class="text-info">Expectations on Implementation</span>

* <span class="badge badge-info">Expectation</span> <span class="text-info">**Contribute to the functional code of the product.**</span>
  * User-visible features are preferred, but it is not a strict requirement.:
  * **The enhancement(s) should fit with the rest of the software** (and the target user profile) and should have the consent of the team members. %%You will lose marks if you go 'rogue' and add things that don't fit with the product.%%

<div tags="m--cs2103 m--tic4002" class="indented-level4">

Some examples:

<panel type="seamless" header="Example enhancements" minimized >

  * Add a new feature %%e.g. add the ability to view statistics%%
  * Enhance an existing features in a major way %%e.g. make the command syntax more user friendly and closer to natural language%%
  * A redesign of the GUI %%e.g. make it work like a chat application (note: chat is a form of CLI)%%
  * A redesign of the code %%e.g. Improve the design to improve the code quality.%%

</panel><p/>
</div>

* **Tip: Contribute to all aspects of the project** e.g. write backend code, frontend code, test code, user documentation, and developer documentation. %%Reason: If you limit yourself to certain aspects only, you could lose marks allocated for the aspects you did not do. In addition, the final exam assumes that you are familiar with all aspects of the project.%%

* **Tip: Do _all_ the work related to your enhancement yourself.** %%Reason: If there is no clear division of who did which enhancement, it will be difficult to divide project credit (or assign responsibility for bugs detected by testers) later.%%<br>
  In other words, ==we recommend that the work to be divided primarily based on _features_== rather than _components_. The latter has the risk of a team member becoming a _single point of failure_ and you becoming _too reliant_ on other team members %%e.g., what if the person assigned to an important component doesn't deliver on time?%%.

<div tags="m--cs2103 m--tic4002">

* **Tip: Divide the components of the product among team members**. Notwithstanding the above, you are still recommended to divide the components of the product among team members so that each team member is _in charge_ of one or more components. While others will be modifying those components to fit their features, your role as the _in charge_ of a component is to guide others modifying that component %%(reason: you are supposed to be the most knowledgeable about that component)%% and protect that component from degrading %%e.g., you can review others' changes to your component and suggest possible changes%%.
</div>


#### <span class="badge badge-info">{{ icon_individual }} Individual</span> <span class="text-info">Expectations on Documentation</span>

* **Objective:** showcase your ability to write both _user-facing documentation_ and _developer-facing documentation_.
* <span class="badge badge-info">Expectation</span> <span class="text-info">**Update the User Guide (UG) and the Developer Guide (DG) parts**</span> that are related to the enhancements you added. The minimum requirement is given below. %%(Reason: Evaluators will not be able to give you marks unless there is sufficient evidence of your documentation skills.)%%
  * UG: {{ ug_pages_per_person }} or more pages
  * DG: {{ dg_pages_per_person }} or more pages
* **Tip: If the UG/DG updates for your enhancements are not enough to reach the above requirements**, you can make up the shortfall by documenting 'proposed' features and alternative designs/implementations. 
* <span class="badge badge-info">Expectation</span> <span class="text-info">**Use at least {{ uml_diagrams_per_person }} UML diagrams in your DG updates**</span> i.e., diagrams you added yourself or those you modified significantly.

#### <span class="badge badge-info">{{ icon_individual }} Individual</span> <span class="text-info">Expectations on Testing</span>

<div id="testing-expectations">

* <span class="badge badge-info">Expectation</span> <span class="text-info">**Write _some_ automated tests**</span> so that we can evaluate your ability to write tests.

<div class="indented-level2">

<box>

**:thinking: How much testings is enough?** We expect you to decide. As you learn different types of testing and what they try to achieve, you should decide how much of each type is worth having. Similarly, you can decide to what extent you want to automate tests, depending on the benefits and the effort required.<br>
There is no requirement for a minimum test coverage level. Note that in a high-end production environment you are often required to have at least 90% of the code covered by tests. In this project, it can be less. ==The weaker your tests are, the higher the risk of bugs, which will cost marks if not fixed before the final submission.==
</box>
</div>

</div>

#### <span class="badge badge-info">{{ icon_individual }} Individual</span> <span class="text-info">Expectations on Teamwork</span>

* <span class="badge badge-info">Expectation</span> <span class="text-info">**Do an equal share of the _team-tasks_**.</span>

<div id="team-tasks" class="indented-level2">

<box>

_Team-tasks_ are the tasks that _someone_ in the team has to do.

<panel type="seamless" header="{{ icon_example }} Examples of team-tasks">

<span id="example-team-tasks">

Here is a non-exhaustive list of team-tasks:

1. Setting up the GitHub team org/repo
1. Necessary general code enhancements{% if cs2103 or tic4002 %} e.g.,
   1. Work related to renaming the product
   1. Work related to changing the product icon
   1. Morphing the product into a different product{% endif %}
1. Setting up tools e.g., GitHub, Gradle
1. Maintaining the issue tracker
1. Release management
1. Updating user/developer docs that are not specific to a feature %%e.g. documenting the target user profile%%
1. Incorporating more useful tools/libraries/frameworks into the product or the project workflow %%(e.g. automate more aspects of the project workflow using a GitHub plugin)%%

</span>
</panel><p/>
</box>
</div>

* <span class="badge badge-info">Expectation</span> <span class="text-info">**Carry an equal share of project roles and responsibilities**.</span>

<div class="indented-level2">

<box>
<span id="roles">

_Roles_ indicate aspects you are in charge of and responsible for. %%E.g., if you are in charge of documentation, you are the person who should allocate which parts of the documentation is to be done by who, ensure the document is in right format, ensure consistency etc.%%

<panel type="seamless" header="{{ icon_example }} Recommended roles and responsibilities">

This is a non-exhaustive list; you may define additional roles.

* _Team lead_: Responsible for overall project coordination.
* _Documentation_ (short for ‘in charge of documentation’): Responsible for the quality of various project documents.
* _Testing_: Ensures the testing of the project is done properly and on time.
* _Code quality_: Looks after code quality, ensures adherence to coding standards, etc.
* _Deliverables and deadlines_: Ensure project deliverables are done on time and in the right format.
* _Integration_: In charge of versioning of the code, maintaining the code repository, integrating various parts of the software to create a whole.
* _Scheduling and tracking_: In charge of defining, assigning, and tracking project tasks.
* _[Tool ABC] expert_: %%e.g. Intellij expert, Git expert, etc.%% Helps other team member with matters related to the specific tool.

<div tags="m--cs2103 m--tic4002">

* _In charge of[Component XYZ]_: %%e.g. In charge of `Model`, `UI`, `Storage`, etc.%% Note that being _in charge_ of a component doesn't mean you are the only one who should be modifying that component. Rather, you are the one who's expected to, know that component best, review changes done to that component in {{ version_penultimate }}-{{ version_final }}, act as the gate keeper of its quality, help others when they face difficulties while modifying that component etc.
</div>
<div tags="m--cs2113 m--tic4001">

* _In charge of[Area XYZ]_ of the code: %%e.g. In charge of the code that deals with storage, etc.%% If you are in charge of an area, you are expected to know that area well, and review changes done to that code.
</div>
</panel><p/>

{{ icon_tip }} Ensure each of the important roles are assigned to one person in the team. It is OK to have a 'backup' for each role, but **for each aspect there should be one person who is unequivocally the person responsible for it**. %%Reason: when _everyone is responsible for everything_, no one is.%%
</span>
</box>
</div>

* <span class="badge badge-info">Expectation</span> <span class="text-info">**Review each others work**.</span> %%Reason: reviewing skills is a learning outcome, and it is mutually beneficial.%%

</span>

</div>

{% endcall %}
