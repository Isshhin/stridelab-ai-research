# StrideLab Engine 1.5 Research Snapshot V2 — Commit Delta Report

- Development Repository: `Isshhin/stridelab-development`
- Previous Snapshot Source Commit: `b79f3f9a835141c6f773810bf9739ae3d0593fe2`
- Frozen V2 Source Commit: `11a59b329341135039a30d24df0d55c8f085cc5d`

## 1. Previously Audited V1 Source Files That Changed (5)

- `native-android/app/src/main/java/io/stridelab/privatealpha/Engine15CoachControls.kt`
- `native-android/app/src/main/java/io/stridelab/privatealpha/Engine15CoachingUi.kt`
- `native-android/app/src/main/java/io/stridelab/privatealpha/Engine15ScheduleReview.kt`
- `native-android/app/src/main/java/io/stridelab/privatealpha/TrainingRepository.kt`
- `native-android/app/src/test/java/io/stridelab/privatealpha/Engine15DailyLoadShaperTest.kt`

## 2. Commit History (`b79f3f9a..11a59b32`)

```text
11a59b32 Implement synchronized AMOLED UI skeleton loaders across primary and detail screens
b78d920c Polish Today, Activity, Training coaching cards, and return-to-origin transitions
c0703101 feat(ui): clean Training/Running headers, multi-color Consistency on Today All, and modern Activity filter pills
aaf8f51d feat(nav): add 5-slot docked AMOLED navigation bar, Quick-Log sheet, and Activity tab
1f712a2a feat(ui): add Anatomical Muscle Map v1 with exercise info sheet and session focus
75ce697e feat(workout): add Strength/Calisthenics progression projectors, set-table default, and scoped hold timer
5defc09e docs: build Obsidian Knowledge Graph and context-pack compiler
36a5eeb8 ui: redesign Share Studio canvas renderer and dark studio tray
2c2be9af ui: polish GPS cache, More profile display, calendar strip, and Hevy-grade logger
528970a0 UI Modernization 1.0 (Phase 0 + Phase 1): AMOLED foundation, Hevy-grade logger, flattened core screens
263de3ff Fit workout history filters to enlarged text
8818cd65 Unify completed workout history and baseline suggestions
80e7d634 Schedule custom workouts in the Training calendar
e5a26ac0 Add reusable workout templates and compact set logging
ab04ac48 Add Freeform workout logging to Training
```

## 3. Diff Statistics (`b79f3f9a..11a59b32`)

```text
AGENTS.md                                          |   13 +-
 docs/context-packs/STRIDELAB_ENGINE_PACK.md        |  339 ++++
 docs/context-packs/STRIDELAB_FULL_CONTEXT.md       |  764 ++++++++
 docs/context-packs/STRIDELAB_SHARESTUDIO_PACK.md   |  220 +++
 docs/context-packs/STRIDELAB_UI_PACK.md            |  262 +++
 docs/wiki/00-StrideLab-Index.md                    |   62 +
 docs/wiki/architecture.md                          |   61 -
 docs/wiki/architecture/App-Architecture.md         |   64 +
 docs/wiki/architecture/Engine-1.5.md               |   49 +
 docs/wiki/architecture/Hard-Guardrails.md          |   47 +
 .../wiki/architecture/Storage-and-FIT-Contracts.md |   56 +
 ...5-Isolation-from-Freeform-and-Custom-Logging.md |   29 +
 .../ADR-02-GPS-200m-Default-Privacy-Trimming.md    |   30 +
 ...03-Offline-First-Independent-Local-Ownership.md |   29 +
 ...dant-UI-While-Preserving-Unified-Data-Layers.md |   39 +
 docs/wiki/engine-rules.md                          |  107 --
 docs/wiki/features/Freeform-Logger.md              |   35 +
 docs/wiki/features/Garmin-and-Activity-Import.md   |   41 +
 .../features/Guided-Workout-Player-and-Debrief.md  |   33 +
 docs/wiki/features/Progress-and-History.md         |   33 +
 docs/wiki/features/Share-Studio.md                 |   43 +
 docs/wiki/features/Templates-and-Custom-Planner.md |   35 +
 docs/wiki/index.md                                 |   66 -
 docs/wiki/roadmap/Anatomical-Muscle-Map.md         |   59 +
 docs/wiki/roadmap/Main-and-Supporting-Plans.md     |   30 +
 .../roadmap/Strength-and-Calisthenics-Overhaul.md  |   50 +
 docs/wiki/screens.md                               |   71 -
 docs/wiki/ui-system.md                             |   53 -
 docs/wiki/ui/Screens-Map.md                        |   49 +
 docs/wiki/ui/UI-Design-System.md                   |   52 +
 .../privatealpha/AmoledWorkoutPlayerTest.kt        |    7 +
 .../privatealpha/AnatomicalMuscleMapUiTest.kt      |  247 +++
 .../privatealpha/CoachedSetTableUiTest.kt          |  204 +++
 .../stridelab/privatealpha/CustomPlannerUiTest.kt  |  159 ++
 .../privatealpha/Engine15CoachControlsTest.kt      |    6 +-
 .../stridelab/privatealpha/FreeformLoggerUiTest.kt |  279 +++
 .../privatealpha/FreeformProcessRestartTest.kt     |   96 +
 .../privatealpha/FreeformStorageAndroidTest.kt     |  258 +++
 .../stridelab/privatealpha/NativeNavigationTest.kt |    3 +-
 .../privatealpha/NavigationShellUiTest.kt          |  460 +++++
 .../privatealpha/SharePhotoRendererAndroidTest.kt  |   45 +
 .../io/stridelab/privatealpha/ShareStudioUiTest.kt |   27 +
 .../privatealpha/SkeletonLoadersUiTest.kt          |  239 +++
 .../stridelab/privatealpha/TracksideTodayTest.kt   |    3 +-
 .../privatealpha/UiModernizationAcceptanceTest.kt  |  194 ++
 .../privatealpha/WorkoutEvidenceUiTest.kt          |  114 ++
 .../privatealpha/ActivityHistoryTabScreen.kt       |  566 ++++++
 .../privatealpha/ActivityThumbnailCache.kt         |  167 ++
 .../stridelab/privatealpha/AnatomicalMuscleMap.kt  |  534 ++++++
 .../io/stridelab/privatealpha/BlueprintWorkout.kt  |   11 +
 .../io/stridelab/privatealpha/CoachedSetTable.kt   |  814 +++++++++
 .../stridelab/privatealpha/CustomPlannerScreens.kt |  368 ++++
 .../privatealpha/CustomWorkoutSchedule.kt          |  157 ++
 .../stridelab/privatealpha/DurableWorkoutPlayer.kt |  124 +-
 .../privatealpha/Engine15CoachControls.kt          |  624 ++++++-
 .../stridelab/privatealpha/Engine15CoachingUi.kt   |   21 +-
 .../privatealpha/Engine15ScheduleReview.kt         |  311 +++-
 .../io/stridelab/privatealpha/ExerciseInfoSheet.kt |  284 +++
 .../io/stridelab/privatealpha/FreeformAccess.kt    |   91 +
 .../io/stridelab/privatealpha/FreeformEditor.kt    | 1914 ++++++++++++++++++++
 .../io/stridelab/privatealpha/FreeformScreens.kt   |  735 ++++++++
 .../io/stridelab/privatealpha/FreeformWorkout.kt   |  311 ++++
 .../privatealpha/ManualDisciplineStore.kt          |  236 ++-
 .../privatealpha/ManualWorkoutTemplates.kt         |  183 +-
 .../stridelab/privatealpha/MuscleFocusProjector.kt |  298 +++
 .../stridelab/privatealpha/NativeMainActivity.kt   |  425 ++++-
 .../java/io/stridelab/privatealpha/PlanBuilder.kt  |   37 +-
 .../io/stridelab/privatealpha/QuickLogSheet.kt     |  253 +++
 .../io/stridelab/privatealpha/ShareCardRenderer.kt |  666 +++++--
 .../io/stridelab/privatealpha/ShareStudioScreen.kt | 1560 +++++++++++-----
 .../StrengthCalisthenicsProgression.kt             |  434 +++++
 .../io/stridelab/privatealpha/StrideApplication.kt |    2 +
 .../stridelab/privatealpha/StrideLabTodayScreen.kt |   97 +-
 .../privatealpha/StrideLabUiPrimitives.kt          | 1028 +++++++++++
 .../StrideLabUnifiedTrainingTimeline.kt            |  548 ++++--
 .../stridelab/privatealpha/StrideLabVisualKit.kt   |  202 ++-
 .../privatealpha/TodayAdaptiveDashboard.kt         |  369 ++--
 .../privatealpha/TodayDisciplineDashboard.kt       |  170 +-
 .../java/io/stridelab/privatealpha/TodayStartup.kt |   57 +
 .../privatealpha/TracksideActivityDetailSurface.kt |   12 +
 .../privatealpha/TracksideBuilderScreens.kt        |    1 +
 .../privatealpha/TracksideFloatingNavigation.kt    |  277 ++-
 .../stridelab/privatealpha/TracksideManagePlan.kt  |   30 -
 .../stridelab/privatealpha/TracksideMoreScreen.kt  |   41 +-
 .../privatealpha/TracksideParityPausedPlan.kt      |    1 -
 .../privatealpha/TracksideScrollActivityContent.kt |   33 +-
 .../TracksideStationaryActivityDetail.kt           |   22 +-
 .../privatealpha/TracksideTrainingCalendar.kt      |   46 +-
 .../privatealpha/TracksideTrainingHubHeader.kt     |  290 +--
 .../java/io/stridelab/privatealpha/TracksideUi.kt  |   16 +-
 .../stridelab/privatealpha/TrainingRepository.kt   |  131 +-
 .../io/stridelab/privatealpha/WorkoutEvidence.kt   |  280 +++
 .../privatealpha/WorkoutEvidenceScreen.kt          |   69 +
 .../stridelab/privatealpha/WorkoutPlayerEngine.kt  |   97 +
 .../io/stridelab/privatealpha/WorkoutScreen.kt     |  121 +-
 .../privatealpha/WorkoutTemplateScreens.kt         |  538 ++++++
 .../ConsistencyDisciplineProjectionTest.kt         |  101 ++
 .../io/stridelab/privatealpha/CustomPlannerTest.kt |   72 +
 .../privatealpha/Engine15DailyLoadShaperTest.kt    |   15 +-
 .../stridelab/privatealpha/FreeformWorkoutTest.kt  |   81 +
 .../privatealpha/MuscleFocusProjectorTest.kt       |  144 ++
 .../StrengthCalisthenicsProgressionTest.kt         |  192 ++
 .../privatealpha/UiModernizationUnitTest.kt        |  119 ++
 .../WorkoutEvidenceCardProjectionTest.kt           |  108 ++
 .../stridelab/privatealpha/WorkoutEvidenceTest.kt  |   96 +
 .../WorkoutPlayerEngineOverhaulTest.kt             |   93 +
 .../stridelab/privatealpha/WorkoutRoutineTest.kt   |   73 +
 scripts/compile_context_packs.py                   |  421 +++++
 108 files changed, 20157 insertions(+), 2122 deletions(-)
```
