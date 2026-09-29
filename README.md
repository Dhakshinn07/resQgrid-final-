# ResQGrid — Independent Data-Driven Prototype v2.1

A working prototype for continuous civic issue management, pre-disaster risk analysis, disaster response, emergency coordination and post-disaster recovery.

## Principles
- No preloaded complaints, incidents, buildings or locations.
- User reports, selected coordinates and uploaded photos are the source data.
- AI/rules extract multiple hazards, departments and potential impact chains from the actual complaint.
- Work order is risk-based: immediate hazards that can endanger workers are addressed before dependent work. Example: exposed electrical wires near reported water -> electrical safety/isolation before drainage work.
- All predictions are potential scenarios, not guarantees that a disaster will happen.

## Run
### Frontend
```powershell
cd frontend
npm.cmd install
npm.cmd run dev
```
Open http://localhost:5173

### Backend (second terminal)
```powershell
cd backend
npm.cmd install
npm.cmd run dev
```
Runs on http://localhost:5000

Optional: copy `.env.example` to `.env` and add `OPENAI_API_KEY` for LLM-assisted analysis. Without it, the local deterministic risk engine works from user-entered complaint text.

## Data
Runtime data is stored in `backend/data.json` and uploaded evidence in `backend/uploads/`. These are created as users use the system; there is no seeded demo incident dataset.

## Production boundary
Live ambulance dispatch, authoritative government disaster feeds, official road-closure feeds, and emergency-service availability require real external/institutional integrations. This prototype does not fake those integrations.
