# MacroLens AI

MacroLens AI is a professional AI-powered nutrition platform for the Hispanic market, founded by Benjamin Salvatierra. The MVP is designed as a scalable mobile product: food scanning, nutrition estimates, meal history, SmartPlate recommendations, AI coaching, dashboards, and a freemium subscription layer.

## Stack

- Flutter and Dart for mobile.
- Riverpod for state management.
- GoRouter for navigation.
- Supabase Auth, PostgreSQL, Storage, and Edge Functions.
- OpenAI-compatible AI architecture with mock and real service boundaries.
- Prepared interfaces for Stripe, Mercado Pago, RevenueCat, OneSignal, and Firebase Analytics.

## Setup

```powershell
cd apps/mobile
flutter pub get
```

Create `apps/mobile/.env` from `apps/mobile/.env.example` and set Supabase/OpenAI values when available. The app runs with mock services by default.

Runtime configuration currently uses `--dart-define` values:

```powershell
flutter run `
  --dart-define=USE_MOCK_SERVICES=true `
  --dart-define=SUPABASE_URL= `
  --dart-define=SUPABASE_ANON_KEY=
```

## Run

```powershell
cd apps/mobile
flutter run
```

If platform folders are missing because Flutter was not available during scaffolding, run:

```powershell
cd apps/mobile
flutter create --project-name macrolens_ai --platforms=android,ios .
flutter pub get
```

## Test

```powershell
cd apps/mobile
dart format lib test
flutter analyze
flutter test
```

## Project Structure

- `apps/mobile`: Flutter application.
- `packages/design_system`: Shared design tokens placeholder.
- `packages/core`: Core contracts placeholder.
- `packages/shared`: Shared cross-app models placeholder.
- `packages/ai`: AI orchestration placeholder.
- `packages/nutrition`: Nutrition domain placeholder.
- `backend/supabase`: Migrations, seed data, and Edge Function stubs.
- `docs`: Product, architecture, AI, database, API, design, and roadmap documentation.

## MVP Status

Implemented base Clean Architecture, mock authentication, premium onboarding profile capture with restrictions/preferences, redesigned home dashboard, mock/Edge Function meal analysis, premium reusable analysis result UI, meal history with filters, daily/weekly nutrition summary use case, AI coach pipeline with premium chat UI, SmartPlate premium guard, redesigned subscription/paywall, Supabase SQL migrations, Edge Function contracts, and basic tests.

## Design System

The mobile app now includes a centralized premium design system:

- Theme tokens: colors, typography, spacing, radius, shadows, and gradients.
- Components: premium buttons, cards, badges, text fields, loaders, macro cards, progress cards, AI insight cards, and empty states.
- Light and dark theme preparation.

## Next Steps

1. Install Flutter/Dart and generate platform folders if needed.
2. Run formatter, analyzer, and tests in a machine with Flutter available.
3. Configure Supabase project values, bucket `meal-images`, and migrations.
4. Replace mock AI/auth/payment services with production implementations.
5. Add camera permissions and native app icons.
6. Wire RevenueCat, Stripe, or Mercado Pago.
7. Add OneSignal and Firebase Analytics.
