# Applied Energistics 3 Documentation

This is Applied Energistics 3 code Documentation. Here you will find both API documentation, if you wish to use AE3 API, and internal documentation, if you wish to contribute to AE3. Use the switch in the top right corner to switch between which type of documentation is displayed.

{% method %}
{% sample lang="api" %}
Right now you are reading: **API Documentation**.

## Adding AE3 to your workspace

_Not yet implemented. Either clone the repo, run `gradle build`, take the dev jar and add it as local dependency or download all the sources and throw them into src/api._

{% sample lang="internal" %}
Right now you are reading: **Internal Documentation**.

## Setting up AE3 development workspace

### Eclipse
1. Clone the repo
2. Download Forge MDK and copy "eclipse" folder from it into cloned repo
3. Run `gradle setupDecompWorkspace eclipse`
4. Point eclipse to "eclipse" folder inside the repo

### IDEA
1. Clone the repo
2. Launch idea, click open project, select "build.gradle" inside the repo, Open As Project
3. **DESELECT "Create separate module per source set"**
4. (Optionally) Select "Create directories for empty..."
5. If AE still does not come with gradle wrapper, use your local gradle installation or copy gradle wrapper from default forge MDK
6. Run "Tasks/forgegradle/setupDecompWorkspace". You may want to create run configuration, if you're going to be updating dependencies often
7. Run "Tasks/forgegradle/genIntellijRuns", there is no need to run it more than once even after workspace update

Based on CPW's Forge MDK Intellij Setup Tutorial:
[![Tutorial](https://i.ytimg.com/vi/G2aPT36kf60/hqdefault.jpg)](https://youtu.be/G2aPT36kf60)

{% endmethod %}