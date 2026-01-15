// @ts-nocheck
import React, { useMemo, useState } from "react";

/**
 * Prototype: 근무시간 관리 + "시간 기준 만들기" Wizard (Modal)
 * - 메인: 리스트/상세(읽기/편집)
 * - +시간 기준 추가: 4-step 모달
 *   1) 기본 정보
 *   2) 기준 설정
 *   3) 근무 유형 설정 (기본 근무는 고정 선택, 추가 선택 시 하단 설정 섹션이 등장)
 *   4) 기준 미리보기/생성
 */

const Chip = ({ tone = "slate", children }) => {
  const tones = {
    slate: "bg-slate-100 text-slate-600",
    blue: "bg-blue-100 text-blue-700",
    purple: "bg-purple-100 text-purple-700",
    pink: "bg-pink-100 text-pink-700",
    orange: "bg-orange-100 text-orange-700",
    green: "bg-emerald-100 text-emerald-700",
  };
  return (
    <span className={`inline-flex items-center rounded-full px-2 py-0.5 text-xs font-semibold ${tones[tone] || tones.slate}`}>
      {children}
    </span>
  );
};

const FieldRow = ({ label, required, children, hint }) => (
  <div className="grid grid-cols-12 items-start gap-3 py-2">
    <div className="col-span-12 md:col-span-3">
      <div className="text-sm font-medium text-slate-700 break-keep">
        {label} {required ? <span className="text-rose-600">*</span> : null}
      </div>
      {hint ? <div className="mt-0.5 text-xs text-slate-500 break-keep">{hint}</div> : null}
    </div>
    <div className="col-span-12 md:col-span-9">{children}</div>
  </div>
);

const Seg = ({ value, setValue, items }) => (
  <div className="inline-flex rounded-lg bg-slate-100 p-1">
    {items.map((it) => {
      const active = it.value === value;
      return (
        <button
          key={it.value}
          onClick={() => setValue(it.value)}
          className={`px-3 py-1.5 text-sm font-semibold rounded-md transition ${
            active ? "bg-white shadow-sm text-slate-900" : "text-slate-600 hover:text-slate-800"
          }`}
        >
          {it.label}
        </button>
      );
    })}
  </div>
);

const Toggle = ({ checked, onChange, disabled }) => (
  <button
    type="button"
    aria-pressed={checked}
    onClick={() => !disabled && onChange(!checked)}
    className={`relative inline-flex h-6 w-11 items-center rounded-full transition ${
      disabled ? "bg-slate-200 cursor-not-allowed" : checked ? "bg-emerald-500" : "bg-slate-300"
    }`}
  >
    <span
      className={`inline-block h-5 w-5 transform rounded-full bg-white transition ${
        checked ? "translate-x-5" : "translate-x-1"
      }`}
    />
  </button>
);

const Select = ({ value, onChange, options, disabled }) => (
  <select
    className={`w-full rounded-lg border px-3 py-2 text-sm outline-none focus:ring-2 focus:ring-slate-200 ${
      disabled ? "bg-slate-100 text-slate-400" : "bg-white"
    }`}
    value={value}
    onChange={(e) => onChange(e.target.value)}
    disabled={disabled}
  >
    {options.map((o) => (
      <option key={o.value} value={o.value}>
        {o.label}
      </option>
    ))}
  </select>
);

const Input = ({ value, onChange, placeholder, disabled }) => (
  <input
    className={`w-full rounded-lg border px-3 py-2 text-sm outline-none focus:ring-2 focus:ring-slate-200 ${
      disabled ? "bg-slate-100 text-slate-400" : "bg-white"
    }`}
    value={value}
    onChange={(e) => onChange(e.target.value)}
    placeholder={placeholder}
    disabled={disabled}
  />
);

const Radio = ({ checked, onChange, label, disabled }) => (
  <label className={`flex items-center gap-2 text-sm ${disabled ? "text-slate-400" : "text-slate-700"}`}>
    <input type="radio" checked={checked} onChange={() => onChange(true)} disabled={disabled} />
    <span className="break-keep">{label}</span>
  </label>
);

const Check = ({ checked, onChange, label, disabled }) => (
  <label className={`flex items-center gap-2 text-sm ${disabled ? "text-slate-400" : "text-slate-700"}`}>
    <input type="checkbox" className="h-4 w-4" checked={checked} onChange={(e) => onChange(e.target.checked)} disabled={disabled} />
    <span className="break-keep">{label}</span>
  </label>
);

const BadgeUse = ({ use }) => (
  <span className={`text-xs font-bold ${use ? "text-blue-700" : "text-slate-500"}`}>{use ? "사용중" : "미사용"}</span>
);

const Card = ({ active, title, subtitle, chips = [], use, onClick }) => (
  <button
    type="button"
    onClick={onClick}
    className={`w-full text-left rounded-xl border px-4 py-3 transition ${
      active ? "border-blue-300 bg-blue-50" : "border-slate-200 bg-white hover:bg-slate-50"
    }`}
  >
    <div className="flex items-start justify-between gap-3">
      <div className="min-w-0">
        <div className="flex items-center gap-2 flex-wrap">
          <div className="text-sm font-bold text-slate-900 truncate">{title}</div>
          <div className="flex items-center gap-1 flex-wrap">
            {chips.map((c, idx) => (
              <Chip key={idx} tone={c.tone}>
                {c.label}
              </Chip>
            ))}
          </div>
        </div>
        <div className="mt-1 text-xs text-slate-500 break-keep">{subtitle}</div>
      </div>
      <BadgeUse use={use} />
    </div>
  </button>
);

const Section = ({ title, children, right }) => (
  <div className="rounded-2xl border border-slate-200 bg-white">
    <div className="flex items-center justify-between px-5 py-4 border-b border-slate-100">
      <div className="text-sm font-bold text-slate-900 break-keep">{title}</div>
      {right}
    </div>
    <div className="px-5 py-4">{children}</div>
  </div>
);

const StepPill = ({ done, active, label }) => (
  <div
    className={`inline-flex items-center gap-2 rounded-full px-3 py-1 text-xs font-bold ${
      active ? "bg-blue-600 text-white" : done ? "bg-emerald-100 text-emerald-800" : "bg-slate-100 text-slate-600"
    }`}
  >
    <span className={`h-2 w-2 rounded-full ${active ? "bg-white" : done ? "bg-emerald-600" : "bg-slate-400"}`} />
    {label}
  </div>
);

const SmallTime = ({ value, onChange, disabled }) => (
  <input
    className={`w-[88px] rounded-lg border px-3 py-2 text-sm outline-none focus:ring-2 focus:ring-slate-200 ${
      disabled ? "bg-slate-100 text-slate-400" : "bg-white"
    }`}
    value={value}
    onChange={(e) => onChange(e.target.value)}
    placeholder="00:00"
    disabled={disabled}
  />
);

const ModalShell = ({ open, title, onClose, children, footer }) => {
  if (!open) return null;
  return (
    <div className="fixed inset-0 z-50 flex items-center justify-center">
      <div className="absolute inset-0 bg-slate-900/40" onClick={onClose} />
      <div className="relative w-[min(980px,calc(100vw-40px))] max-h-[calc(100vh-40px)] overflow-hidden rounded-3xl bg-white shadow-2xl">
        <div className="flex items-center justify-between px-6 py-5 border-b border-slate-100">
          <div className="text-lg font-extrabold text-slate-900 break-keep">{title}</div>
          <button
            className="h-10 w-10 rounded-full border border-slate-200 bg-white text-lg"
            onClick={onClose}
            aria-label="닫기"
          >
            ×
          </button>
        </div>
        <div className="px-6 py-5 overflow-auto max-h-[calc(100vh-180px)]">{children}</div>
        <div className="px-6 py-4 border-t border-slate-100 bg-white">{footer}</div>
      </div>
    </div>
  );
};

const toastBase = "fixed bottom-6 left-1/2 -translate-x-1/2 rounded-xl border bg-white px-4 py-3 shadow-lg text-sm";

export default function WorkTimeCriteriaPrototype() {
  const initialData = useMemo(
    () => [
      { id: "c1", title: "기본 근무 기준", subtitle: "일반 근무 시간 계산 기준", tags: [{ label: "기본", tone: "slate" }], use: true, kind: "기본" },
      {
        id: "c2",
        title: "야간 근무 기준",
        subtitle: "야간 근무 계산",
        tags: [
          { label: "기본", tone: "slate" },
          { label: "야간", tone: "blue" },
        ],
        use: true,
        kind: "야간",
      },
      {
        id: "c3",
        title: "휴일 근무 기준",
        subtitle: "연장근무 계산",
        tags: [
          { label: "기본", tone: "slate" },
          { label: "야간", tone: "blue" },
          { label: "휴일", tone: "purple" },
        ],
        use: false,
        kind: "휴일",
      },
      {
        id: "c4",
        title: "휴일연장근무 기준",
        subtitle: "유연 근무용",
        tags: [
          { label: "기본", tone: "slate" },
          { label: "휴일", tone: "purple" },
          { label: "연장", tone: "orange" },
        ],
        use: false,
        kind: "휴일연장",
      },
    ],
    []
  );

  const [criteriaList, setCriteriaList] = useState(initialData);

  const [leftMenu, setLeftMenu] = useState("근무시간 관리");
  const [filterType, setFilterType] = useState("전체");
  const [filterUse, setFilterUse] = useState("전체");
  const [q, setQ] = useState("");

  const filtered = useMemo(() => {
    return criteriaList
      .filter((it) => {
        const typeOk = filterType === "전체" ? true : it.kind === filterType;
        const useOk = filterUse === "전체" ? true : filterUse === "사용" ? it.use === true : it.use === false;
        const qOk = q.trim().length === 0 ? true : (it.title + " " + it.subtitle).toLowerCase().includes(q.trim().toLowerCase());
        return typeOk && useOk && qOk;
      })
      .sort((a, b) => (a.use === b.use ? 0 : a.use ? -1 : 1));
  }, [criteriaList, filterType, filterUse, q]);

  const [selectedId, setSelectedId] = useState("c2");
  const selected = useMemo(() => filtered.find((x) => x.id === selectedId) || criteriaList.find((x) => x.id === selectedId) || criteriaList[0], [filtered, selectedId, criteriaList]);

  const [mode, setMode] = useState("view"); // view | edit
  const [tab, setTab] = useState("기본");

  // detail form (edit)
  const [name, setName] = useState("야간·휴일 근무 기준");
  const [desc, setDesc] = useState("야간 및 휴일 근무 시간 계산 기준");
  const [useStateValue, setUseStateValue] = useState("사용");
  const [unit, setUnit] = useState("1분");
  const [rounding, setRounding] = useState("버림");

  const [workdayRange, setWorkdayRange] = useState("00:00 - 23:59");
  const [excludeEnabled, setExcludeEnabled] = useState(true);
  const [excludeOutside, setExcludeOutside] = useState(true);
  const [excludeMidnight, setExcludeMidnight] = useState(true);

  const [nightStart, setNightStart] = useState("22:00");
  const [nightEnd, setNightEnd] = useState("06:00");
  const [nightAutoEnd, setNightAutoEnd] = useState(true);
  const [nightIntervalMin, setNightIntervalMin] = useState("1");
  const [nightMin, setNightMin] = useState("1");
  const [nightMax, setNightMax] = useState("1");
  const [mergeOther, setMergeOther] = useState(false);

  const [toast, setToast] = useState(null);

  // Wizard modal state
  const [wizardOpen, setWizardOpen] = useState(false);
  const [wizardStep, setWizardStep] = useState(1); // 1~4

  // step1
  const [wName, setWName] = useState("");
  const [wDesc, setWDesc] = useState("");

  // step2
  const [wUnit, setWUnit] = useState("1분");
  const [wRounding, setWRounding] = useState("버림");
  const [wDayStart, setWDayStart] = useState("00:00");
  const [wDayEnd, setWDayEnd] = useState("23:59");

  // step3 (근무 유형 선택)
  const [wSel, setWSel] = useState({ base: true, early: false, overtime: false, night: false, holiday: false });

  // common exclusion (step3)
  const [wExcludeEnabled, setWExcludeEnabled] = useState(true);
  const [wExcludeOutside, setWExcludeOutside] = useState(true);
  const [wExcludeMidnight, setWExcludeMidnight] = useState(true);

  // early
  const [wEarlyMode, setWEarlyMode] = useState("beforeBase"); // beforeBase | fixedRange
  const [wEarlyFixedStart, setWEarlyFixedStart] = useState("00:00");
  const [wEarlyFixedEnd, setWEarlyFixedEnd] = useState("00:00");
  const [wEarlyMinUnit, setWEarlyMinUnit] = useState("1분");
  const [wEarlyMin, setWEarlyMin] = useState("30분");
  const [wEarlyMax, setWEarlyMax] = useState("240분");
  const [wEarlyMergeBase, setWEarlyMergeBase] = useState(false);

  // overtime
  const [wOtMode, setWOtMode] = useState("overBase"); // overBase | fixedOver
  const [wOtFixedOver, setWOtFixedOver] = useState("00:00");
  const [wOtMinUnit, setWOtMinUnit] = useState("1분");
  const [wOtMin, setWOtMin] = useState("30분");
  const [wOtMax, setWOtMax] = useState("240분");
  const [wDupMode, setWDupMode] = useState("split"); // split | maxOnly
  const [wDupMaxMode, setWDupMaxMode] = useState("one"); // one | multi
  const [wDupAllowEarly, setWDupAllowEarly] = useState(false);
  const [wDupAllowNight, setWDupAllowNight] = useState(false);
  const [wDupAllowHoliday, setWDupAllowHoliday] = useState(false);

  // night
  const [wNightStart, setWNightStart] = useState("22:00");
  const [wNightEnd, setWNightEnd] = useState("06:00");
  const [wNightOverDay, setWNightOverDay] = useState(true);
  const [wNightMinUnit, setWNightMinUnit] = useState("1분");
  const [wNightMin, setWNightMin] = useState("30분");
  const [wNightMax, setWNightMax] = useState("240분");
  const [wNightMergeBase, setWNightMergeBase] = useState(false);

  // holiday
  const [wHolidayBasis, setWHolidayBasis] = useState("calendar"); // calendar | custom
  const [wHolidayMinUnit, setWHolidayMinUnit] = useState("1분");
  const [wHolidayMin, setWHolidayMin] = useState("30분");
  const [wHolidayMax, setWHolidayMax] = useState("240분");
  const [wHolidayMergeBase, setWHolidayMergeBase] = useState(false);

  // validation confirm
  const [confirmOpen, setConfirmOpen] = useState(false);

  const canEdit = mode === "edit";

  const selectOptionsType = [
    { value: "전체", label: "전체" },
    { value: "기본", label: "기본" },
    { value: "야간", label: "야간" },
    { value: "휴일", label: "휴일" },
    { value: "휴일연장", label: "휴일+연장" },
  ];
  const selectOptionsUse = [
    { value: "전체", label: "전체" },
    { value: "사용", label: "사용" },
    { value: "미사용", label: "미사용" },
  ];

  const onSave = () => {
    setMode("view");
    setToast({ type: "success", message: "저장 완료" });
    setTimeout(() => setToast(null), 1600);
  };

  const onCancel = () => {
    setMode("view");
    setToast({ type: "info", message: "변경 취소" });
    setTimeout(() => setToast(null), 1400);
  };

  const openWizard = () => {
    setWizardOpen(true);
    setWizardStep(1);
    setWName("");
    setWDesc("");
    setWUnit("1분");
    setWRounding("버림");
    setWDayStart("00:00");
    setWDayEnd("23:59");
    setWSel({ base: true, early: false, overtime: false, night: false, holiday: false });
  };

  const closeWizard = () => setWizardOpen(false);

  const stepDone = (n) => {
    if (n === 1) return wName.trim().length > 0;
    if (n === 2) return true;
    if (n === 3) return true;
    return false;
  };

  const wizardNext = () => {
    if (wizardStep === 1 && wName.trim().length === 0) {
      setToast({ type: "info", message: "기준 이름은 필수입니다" });
      setTimeout(() => setToast(null), 1400);
      return;
    }
    if (wizardStep === 3 && wSel.night) {
      // 간단 검증: 익일 넘김이 OFF일 때 종료 < 시작이면 confirm
      const s = wNightStart.replace(":", "");
      const e = wNightEnd.replace(":", "");
      if (!wNightOverDay && Number(e) < Number(s)) {
        setConfirmOpen(true);
        return;
      }
    }
    setWizardStep((s) => Math.min(4, s + 1));
  };

  const wizardPrev = () => setWizardStep((s) => Math.max(1, s - 1));

  const buildTagsFromWizard = () => {
    const tags = [{ label: "기본", tone: "slate" }];
    if (wSel.early) tags.push({ label: "조기", tone: "green" });
    if (wSel.overtime) tags.push({ label: "연장", tone: "orange" });
    if (wSel.night) tags.push({ label: "야간", tone: "blue" });
    if (wSel.holiday) tags.push({ label: "휴일", tone: "purple" });
    return tags;
  };

  const createCriteria = () => {
    const id = `c${Math.floor(Math.random() * 9000) + 1000}`;
    const kind = wSel.holiday && wSel.overtime ? "휴일연장" : wSel.holiday ? "휴일" : wSel.night ? "야간" : "기본";
    const newItem = {
      id,
      title: wName.trim(),
      subtitle: wDesc.trim() || "근무 시간 계산 기준",
      tags: buildTagsFromWizard(),
      use: true,
      kind,
    };
    setCriteriaList((prev) => [newItem, ...prev]);
    setSelectedId(id);
    setWizardOpen(false);
    setToast({ type: "success", message: "기준 생성 완료" });
    setTimeout(() => setToast(null), 1600);
  };

  const WorkTypeCard = ({ title, desc, required, selected, onToggle, badge }) => (
    <button
      type="button"
      onClick={() => !required && onToggle(!selected)}
      className={`w-full rounded-2xl border px-4 py-3 text-left transition ${
        selected ? "border-blue-500 bg-blue-50" : "border-slate-200 bg-white hover:bg-slate-50"
      } ${required ? "cursor-default" : ""}`}
    >
      <div className="flex items-start justify-between gap-2">
        <div>
          <div className="flex items-center gap-2 flex-wrap">
            <div className="text-sm font-extrabold text-slate-900 break-keep">{title}</div>
            {badge ? <Chip tone={badge.tone}>{badge.label}</Chip> : null}
            {required ? <Chip tone="slate">필수</Chip> : null}
          </div>
          <div className="mt-1 text-xs text-slate-500 break-keep">{desc}</div>
        </div>
        <div className="flex items-center gap-2">
          {required ? (
            <div className="text-xs font-bold text-blue-700">고정</div>
          ) : (
            <div className={`text-xs font-bold ${selected ? "text-blue-700" : "text-slate-500"}`}>{selected ? "선택" : "선택"}</div>
          )}
          <div className={`h-4 w-4 rounded-full border ${selected ? "bg-blue-600 border-blue-600" : "bg-white border-slate-300"}`} />
        </div>
      </div>
    </button>
  );

  const WizardStep3Selections = () => {
    const selectedCount = [wSel.early, wSel.overtime, wSel.night, wSel.holiday].filter(Boolean).length;

    return (
      <div className="space-y-4">
        <div className="rounded-2xl border border-slate-200 bg-slate-50 p-4">
          <div className="text-sm font-extrabold text-slate-900">근무 시간 유형 선택</div>
          <div className="mt-1 text-xs text-slate-500 break-keep">기본 근무는 고정 선택이며, 추가 선택 시 하단에 해당 설정 영역이 표시됩니다.</div>
          <div className="mt-3 grid grid-cols-1 md:grid-cols-5 gap-3">
            <WorkTypeCard
              title="기본 근무"
              desc="기본 근무시간 기준으로 근무를 계산합니다."
              required
              selected
              badge={{ label: "기본", tone: "slate" }}
            />
            <WorkTypeCard
              title="조기 근무"
              desc="시작 시간 이전의 근무를 계산합니다."
              selected={wSel.early}
              onToggle={(v) => setWSel((s) => ({ ...s, early: v }))}
              badge={{ label: "조기", tone: "green" }}
            />
            <WorkTypeCard
              title="연장 근무"
              desc="기본근무 이후의 시간을 근무로 계산합니다."
              selected={wSel.overtime}
              onToggle={(v) => setWSel((s) => ({ ...s, overtime: v }))}
              badge={{ label: "연장", tone: "orange" }}
            />
            <WorkTypeCard
              title="야간 근무"
              desc="야간 시간대를 별도로 계산합니다."
              selected={wSel.night}
              onToggle={(v) => setWSel((s) => ({ ...s, night: v }))}
              badge={{ label: "야간", tone: "blue" }}
            />
            <WorkTypeCard
              title="휴일 근무"
              desc="휴일 근무 시간을 계산합니다."
              selected={wSel.holiday}
              onToggle={(v) => setWSel((s) => ({ ...s, holiday: v }))}
              badge={{ label: "휴일", tone: "purple" }}
            />
          </div>
        </div>

        {/* 공통 설정 */}
        <Section title="공통 설정">
          <div className="flex items-center justify-between">
            <div className="text-sm font-bold text-slate-700">근무 제외 시간 설정</div>
            <Toggle checked={wExcludeEnabled} onChange={setWExcludeEnabled} />
          </div>
          <div className="mt-3 space-y-2">
            <Check checked={wExcludeOutside} onChange={setWExcludeOutside} disabled={!wExcludeEnabled} label="외출 시간 근무에서 제외" />
            <Check checked={wExcludeMidnight} onChange={setWExcludeMidnight} disabled={!wExcludeEnabled} label="중간에 나간 시간 근무에서 제외" />
          </div>
        </Section>

        {/* 선택된 유형만 하단 노출 */}
        {wSel.early ? (
          <Section title="조기 근무 세부 설정">
            <div className="grid grid-cols-12 gap-3 items-start">
              <div className="col-span-12 md:col-span-6">
                <div className="text-sm font-bold text-slate-700">조기근무 기준</div>
                <div className="mt-2 space-y-2">
                  <Radio checked={wEarlyMode === "beforeBase"} onChange={() => setWEarlyMode("beforeBase")} label="기본근무 시작 이전" />
                  <Radio checked={wEarlyMode === "fixedRange"} onChange={() => setWEarlyMode("fixedRange")} label="특정 시간 구간" />
                  {wEarlyMode === "fixedRange" ? (
                    <div className="mt-2 rounded-xl border border-slate-200 bg-slate-50 p-3">
                      <div className="text-xs font-bold text-slate-600 mb-2">특정 시간 구간</div>
                      <div className="flex items-center gap-2 flex-wrap">
                        <span className="text-sm text-slate-600">시작</span>
                        <SmallTime value={wEarlyFixedStart} onChange={setWEarlyFixedStart} />
                        <span className="text-sm text-slate-600">종료</span>
                        <SmallTime value={wEarlyFixedEnd} onChange={setWEarlyFixedEnd} />
                      </div>
                    </div>
                  ) : null}
                </div>
              </div>
              <div className="col-span-12 md:col-span-6">
                <div className="text-sm font-bold text-slate-700">인정 시간 범위</div>
                <div className="mt-2 grid grid-cols-12 gap-3">
                  <div className="col-span-12 md:col-span-4">
                    <div className="text-xs font-bold text-slate-600 mb-1">단위</div>
                    <Select
                      value={wEarlyMinUnit}
                      onChange={setWEarlyMinUnit}
                      options={[{ value: "1분", label: "1분" }, { value: "5분", label: "5분" }, { value: "10분", label: "10분" }, { value: "15분", label: "15분" }, { value: "30분", label: "30분" }]}
                    />
                  </div>
                  <div className="col-span-6 md:col-span-4">
                    <div className="text-xs font-bold text-slate-600 mb-1">분 (최소)</div>
                    <Select
                      value={wEarlyMin}
                      onChange={setWEarlyMin}
                      options={[{ value: "30분", label: "30분" }, { value: "60분", label: "60분" }, { value: "120분", label: "120분" }, { value: "180분", label: "180분" }, { value: "240분", label: "240분" }]}
                    />
                  </div>
                  <div className="col-span-6 md:col-span-4">
                    <div className="text-xs font-bold text-slate-600 mb-1">분 (최대)</div>
                    <Select
                      value={wEarlyMax}
                      onChange={setWEarlyMax}
                      options={[{ value: "30분", label: "30분" }, { value: "60분", label: "60분" }, { value: "120분", label: "120분" }, { value: "180분", label: "180분" }, { value: "240분", label: "240분" }]}
                    />
                  </div>
                </div>
                <div className="mt-3 flex items-center justify-between">
                  <div className="text-sm font-medium text-slate-700">기본 근무 시간으로 합산</div>
                  <Toggle checked={wEarlyMergeBase} onChange={setWEarlyMergeBase} />
                </div>
              </div>
            </div>
          </Section>
        ) : null}

        {wSel.overtime ? (
          <Section title="연장 근무 세부 설정">
            <div className="grid grid-cols-12 gap-4">
              <div className="col-span-12">
                <div className="text-sm font-bold text-slate-700">연장근무 기준</div>
                <div className="mt-2 flex flex-col md:flex-row md:items-center gap-3">
                  <Radio checked={wOtMode === "overBase"} onChange={() => setWOtMode("overBase")} label="기본근무 초과" />
                  <Radio checked={wOtMode === "fixedOver"} onChange={() => setWOtMode("fixedOver")} label="특정시간 초과" />
                  {wOtMode === "fixedOver" ? (
                    <div className="md:ml-auto flex items-center gap-2">
                      <span className="text-sm text-slate-600">초과</span>
                      <SmallTime value={wOtFixedOver} onChange={setWOtFixedOver} />
                    </div>
                  ) : null}
                </div>
              </div>

              <div className="col-span-12 md:col-span-6">
                <div className="text-sm font-bold text-slate-700">인정 시간 범위</div>
                <div className="mt-2 grid grid-cols-12 gap-3">
                  <div className="col-span-12 md:col-span-4">
                    <div className="text-xs font-bold text-slate-600 mb-1">단위</div>
                    <Select
                      value={wOtMinUnit}
                      onChange={setWOtMinUnit}
                      options={[{ value: "1분", label: "1분" }, { value: "5분", label: "5분" }, { value: "10분", label: "10분" }, { value: "15분", label: "15분" }, { value: "30분", label: "30분" }]}
                    />
                  </div>
                  <div className="col-span-6 md:col-span-4">
                    <div className="text-xs font-bold text-slate-600 mb-1">분 (최소)</div>
                    <Select
                      value={wOtMin}
                      onChange={setWOtMin}
                      options={[{ value: "30분", label: "30분" }, { value: "60분", label: "60분" }, { value: "120분", label: "120분" }, { value: "180분", label: "180분" }, { value: "240분", label: "240분" }]}
                    />
                  </div>
                  <div className="col-span-6 md:col-span-4">
                    <div className="text-xs font-bold text-slate-600 mb-1">분 (최대)</div>
                    <Select
                      value={wOtMax}
                      onChange={setWOtMax}
                      options={[{ value: "30분", label: "30분" }, { value: "60분", label: "60분" }, { value: "120분", label: "120분" }, { value: "180분", label: "180분" }, { value: "240분", label: "240분" }]}
                    />
                  </div>
                </div>
              </div>

              <div className="col-span-12 md:col-span-6">
                <div className="text-sm font-bold text-slate-700">중복 기준</div>
                <div className="mt-2 space-y-2">
                  <Radio checked={wDupMode === "split"} onChange={() => setWDupMode("split")} label="근무 유형별 분리 인정" />
                  <Radio checked={wDupMode === "maxOnly"} onChange={() => setWDupMode("maxOnly")} label="최대 1개만 인정" />

                  {wDupMode === "maxOnly" ? (
                    <div className="mt-2 rounded-xl border border-slate-200 bg-slate-50 p-3">
                      <div className="text-xs font-bold text-slate-600 mb-2">중복 시 1개 기준만 적용</div>
                      <div className="space-y-2">
                        <Radio checked={wDupMaxMode === "one"} onChange={() => setWDupMaxMode("one")} label="가장 높은 가중치 1가지만 적용" />
                        <Radio checked={wDupMaxMode === "multi"} onChange={() => setWDupMaxMode("multi")} label="겹친 가중치를 모두 적용" />
                      </div>
                    </div>
                  ) : (
                    <div className="mt-2 rounded-xl border border-slate-200 bg-slate-50 p-3">
                      <div className="text-xs font-bold text-slate-600 mb-2">중복 시 함께 인정 가능</div>
                      <div className="grid grid-cols-1 sm:grid-cols-3 gap-2">
                        <Check checked={wDupAllowEarly} onChange={setWDupAllowEarly} label="조기근무와 중복" disabled={!wSel.early} />
                        <Check checked={wDupAllowNight} onChange={setWDupAllowNight} label="야간근무와 중복" disabled={!wSel.night} />
                        <Check checked={wDupAllowHoliday} onChange={setWDupAllowHoliday} label="휴일근무와 중복" disabled={!wSel.holiday} />
                      </div>
                      <div className="mt-1 text-xs text-slate-500 break-keep">선택한 근무 유형만 중복 옵션을 활성화할 수 있습니다.</div>
                    </div>
                  )}
                </div>
              </div>
            </div>
          </Section>
        ) : null}

        {wSel.night ? (
          <Section title="야간 근무 세부 설정">
            <div className="grid grid-cols-12 gap-3">
              <div className="col-span-12 md:col-span-6">
                <div className="text-sm font-bold text-slate-700">야간 근무 구간</div>
                <div className="mt-2 flex items-center gap-2 flex-wrap">
                  <SmallTime value={wNightStart} onChange={setWNightStart} />
                  <span className="text-slate-400">-</span>
                  <SmallTime value={wNightEnd} onChange={setWNightEnd} />
                  <label className="ml-1 flex items-center gap-2 text-sm text-slate-700">
                    <input type="checkbox" checked={wNightOverDay} onChange={(e) => setWNightOverDay(e.target.checked)} />
                    익일 넘어감(+1일)
                  </label>
                </div>
              </div>

              <div className="col-span-12 md:col-span-6">
                <div className="text-sm font-bold text-slate-700">인정 시간 범위</div>
                <div className="mt-2 grid grid-cols-12 gap-3">
                  <div className="col-span-12 md:col-span-4">
                    <div className="text-xs font-bold text-slate-600 mb-1">단위</div>
                    <Select
                      value={wNightMinUnit}
                      onChange={setWNightMinUnit}
                      options={[{ value: "1분", label: "1분" }, { value: "5분", label: "5분" }, { value: "10분", label: "10분" }, { value: "15분", label: "15분" }, { value: "30분", label: "30분" }]}
                    />
                  </div>
                  <div className="col-span-6 md:col-span-4">
                    <div className="text-xs font-bold text-slate-600 mb-1">분 (최소)</div>
                    <Select
                      value={wNightMin}
                      onChange={setWNightMin}
                      options={[{ value: "30분", label: "30분" }, { value: "60분", label: "60분" }, { value: "120분", label: "120분" }, { value: "180분", label: "180분" }, { value: "240분", label: "240분" }]}
                    />
                  </div>
                  <div className="col-span-6 md:col-span-4">
                    <div className="text-xs font-bold text-slate-600 mb-1">분 (최대)</div>
                    <Select
                      value={wNightMax}
                      onChange={setWNightMax}
                      options={[{ value: "30분", label: "30분" }, { value: "60분", label: "60분" }, { value: "120분", label: "120분" }, { value: "180분", label: "180분" }, { value: "240분", label: "240분" }]}
                    />
                  </div>
                </div>
                <div className="mt-3 flex items-center justify-between">
                  <div className="text-sm font-medium text-slate-700">기본 근무 시간으로 합산</div>
                  <Toggle checked={wNightMergeBase} onChange={setWNightMergeBase} />
                </div>
              </div>
            </div>
          </Section>
        ) : null}

        {wSel.holiday ? (
          <Section title="휴일 근무 세부 설정">
            <div className="grid grid-cols-12 gap-4">
              <div className="col-span-12 md:col-span-6">
                <div className="text-sm font-bold text-slate-700">휴일 판별 기준</div>
                <div className="mt-2 space-y-2">
                  <Radio checked={wHolidayBasis === "calendar"} onChange={() => setWHolidayBasis("calendar")} label="공휴일 캘린더" />
                  <Radio checked={wHolidayBasis === "custom"} onChange={() => setWHolidayBasis("custom")} label="사용자 지정" />
                </div>
              </div>

              <div className="col-span-12 md:col-span-6">
                <div className="text-sm font-bold text-slate-700">인정 시간 범위</div>
                <div className="mt-2 grid grid-cols-12 gap-3">
                  <div className="col-span-12 md:col-span-4">
                    <div className="text-xs font-bold text-slate-600 mb-1">단위</div>
                    <Select
                      value={wHolidayMinUnit}
                      onChange={setWHolidayMinUnit}
                      options={[{ value: "1분", label: "1분" }, { value: "5분", label: "5분" }, { value: "10분", label: "10분" }, { value: "15분", label: "15분" }, { value: "30분", label: "30분" }]}
                    />
                  </div>
                  <div className="col-span-6 md:col-span-4">
                    <div className="text-xs font-bold text-slate-600 mb-1">분 (최소)</div>
                    <Select
                      value={wHolidayMin}
                      onChange={setWHolidayMin}
                      options={[{ value: "30분", label: "30분" }, { value: "60분", label: "60분" }, { value: "120분", label: "120분" }, { value: "180분", label: "180분" }, { value: "240분", label: "240분" }]}
                    />
                  </div>
                  <div className="col-span-6 md:col-span-4">
                    <div className="text-xs font-bold text-slate-600 mb-1">분 (최대)</div>
                    <Select
                      value={wHolidayMax}
                      onChange={setWHolidayMax}
                      options={[{ value: "30분", label: "30분" }, { value: "60분", label: "60분" }, { value: "120분", label: "120분" }, { value: "180분", label: "180분" }, { value: "240분", label: "240분" }]}
                    />
                  </div>
                </div>
                <div className="mt-3 flex items-center justify-between">
                  <div className="text-sm font-medium text-slate-700">기본 근무 시간으로 합산</div>
                  <Toggle checked={wHolidayMergeBase} onChange={setWHolidayMergeBase} />
                </div>
              </div>
            </div>
          </Section>
        ) : null}

        <div className="text-xs text-slate-500">선택된 추가 유형: <span className="font-bold text-slate-700">{selectedCount}개</span></div>
      </div>
    );
  };

  const WizardStep4Preview = () => {
    const rows = [
      { key: "기본근무", on: true, note: "기본 근무" },
      { key: "조기근무", on: wSel.early, note: wSel.early ? (wEarlyMode === "beforeBase" ? "기본근무 시작 이전" : `특정 구간 ${wEarlyFixedStart}~${wEarlyFixedEnd}`) : "" },
      { key: "연장근무", on: wSel.overtime, note: wSel.overtime ? (wOtMode === "overBase" ? "기본근무 초과" : `특정시간 초과 ${wOtFixedOver}`) : "" },
      { key: "야간근무", on: wSel.night, note: wSel.night ? `${wNightStart}~${wNightEnd}${wNightOverDay ? " (+1일)" : ""}` : "" },
      { key: "휴일근무", on: wSel.holiday, note: wSel.holiday ? (wHolidayBasis === "calendar" ? "공휴일 캘린더 기준" : "사용자 지정") : "" },
    ];

    return (
      <div className="space-y-4">
        <Section title="기본 정보">
          <div className="grid grid-cols-12 gap-3 text-sm">
            <div className="col-span-12 md:col-span-6"><span className="text-slate-500">기준명</span> <span className="ml-2 font-bold">{wName || "-"}</span></div>
            <div className="col-span-12 md:col-span-6"><span className="text-slate-500">설명</span> <span className="ml-2 font-bold">{wDesc || "-"}</span></div>
            <div className="col-span-12 md:col-span-6"><span className="text-slate-500">시간 산출 단위</span> <span className="ml-2 font-bold">{wUnit}</span></div>
            <div className="col-span-12 md:col-span-6"><span className="text-slate-500">반올림 방식</span> <span className="ml-2 font-bold">{wRounding}</span></div>
            <div className="col-span-12"><span className="text-slate-500">당일 근태 처리 구간</span> <span className="ml-2 font-bold">{wDayStart} - {wDayEnd}</span></div>
          </div>
        </Section>

        <Section title="근무 시간 계산 결과">
          <div className="rounded-2xl border border-slate-200 overflow-hidden">
            <div className="grid grid-cols-12 bg-slate-50 px-4 py-2 text-xs font-bold text-slate-600">
              <div className="col-span-5">근무 유형</div>
              <div className="col-span-2">상태</div>
              <div className="col-span-5">설정 요약</div>
            </div>
            {rows.map((r, idx) => (
              <div key={idx} className="grid grid-cols-12 px-4 py-3 border-t border-slate-100 text-sm">
                <div className="col-span-5 font-bold text-slate-800">{r.key}</div>
                <div className={`col-span-2 font-extrabold ${r.on ? "text-blue-700" : "text-slate-400"}`}>{r.on ? "사용" : "미사용"}</div>
                <div className="col-span-5 text-slate-600 break-keep">{r.note}</div>
              </div>
            ))}
          </div>
        </Section>

        <Section title="근무 시간 적용 기준 요약">
          <div className="grid grid-cols-12 gap-3 text-sm">
            <div className="col-span-12 md:col-span-6">
              <div className="text-slate-500">중복 적용</div>
              <div className="mt-1 font-bold text-slate-800 break-keep">
                {wSel.overtime ? (wDupMode === "split" ? "근무 유형별 분리 인정" : "최대 1개만 인정") : "-"}
              </div>
            </div>
            <div className="col-span-12 md:col-span-6">
              <div className="text-slate-500">근무 제외</div>
              <div className="mt-1 font-bold text-slate-800 break-keep">
                {wExcludeEnabled ? [wExcludeOutside ? "외출 시간" : null, wExcludeMidnight ? "중간 이탈 시간" : null].filter(Boolean).join(", ") || "-" : "미사용"}
              </div>
            </div>
          </div>
        </Section>
      </div>
    );
  };

  const WizardBody = () => {
    return (
      <div className="space-y-4">
        <div className="flex items-center gap-2 flex-wrap">
          <StepPill done={wizardStep > 1 && stepDone(1)} active={wizardStep === 1} label="1 기본 정보" />
          <StepPill done={wizardStep > 2} active={wizardStep === 2} label="2 기준 설정" />
          <StepPill done={wizardStep > 3} active={wizardStep === 3} label="3 근무 유형 설정" />
          <StepPill done={false} active={wizardStep === 4} label="4 기준 미리보기" />
        </div>

        {wizardStep === 1 ? (
          <Section title="근무 시간 기준 정보">
            <FieldRow label="기준 이름" required>
              <Input value={wName} onChange={setWName} placeholder="예: 기본 근무 기준 (1)" />
            </FieldRow>
            <FieldRow label="설명">
              <Input value={wDesc} onChange={setWDesc} placeholder="예: 사무직 기본 근무 시간 계산" />
            </FieldRow>
          </Section>
        ) : null}

        {wizardStep === 2 ? (
          <Section title="기준 설정">
            <FieldRow label="시간 산출 단위" required>
              <div className="grid grid-cols-1 md:grid-cols-5 gap-2">
                {["1분", "10분", "15분", "30분"].map((v) => (
                  <label key={v} className="flex items-center gap-2 rounded-xl border border-slate-200 bg-white px-3 py-2 text-sm">
                    <input type="radio" checked={wUnit === v} onChange={() => setWUnit(v)} />
                    {v}
                  </label>
                ))}
              </div>
            </FieldRow>

            <FieldRow label="반올림 방식" required>
              <div className="grid grid-cols-1 md:grid-cols-4 gap-2">
                {["버림", "반올림", "올림"].map((v) => (
                  <label key={v} className="flex items-center gap-2 rounded-xl border border-slate-200 bg-white px-3 py-2 text-sm">
                    <input type="radio" checked={wRounding === v} onChange={() => setWRounding(v)} />
                    {v}
                  </label>
                ))}
              </div>
            </FieldRow>

            <FieldRow
              label="당일 근태 처리 구간"
              required
              hint="해당 구간에 포함되는 출퇴근 기록을 근무로 계산합니다. (예: 종료를 초과한 기록은 다음 날로 분리)"
            >
              <div className="flex items-center gap-2 flex-wrap">
                <SmallTime value={wDayStart} onChange={setWDayStart} />
                <span className="text-slate-400">-</span>
                <SmallTime value={wDayEnd} onChange={setWDayEnd} />
              </div>
            </FieldRow>
          </Section>
        ) : null}

        {wizardStep === 3 ? <WizardStep3Selections /> : null}

        {wizardStep === 4 ? <WizardStep4Preview /> : null}
      </div>
    );
  };

  const WizardFooter = () => {
    const nextDisabled = wizardStep === 1 && wName.trim().length === 0;
    return (
      <div className="flex items-center justify-between gap-3">
        <button
          onClick={wizardPrev}
          className={`rounded-lg border border-slate-200 bg-white px-4 py-2 text-sm font-bold ${wizardStep === 1 ? "opacity-40 cursor-not-allowed" : ""}`}
          disabled={wizardStep === 1}
        >
          이전
        </button>

        <div className="flex items-center gap-2">
          {wizardStep < 4 ? (
            <button
              onClick={wizardNext}
              className={`rounded-lg bg-blue-600 px-4 py-2 text-sm font-extrabold text-white ${nextDisabled ? "opacity-60 cursor-not-allowed" : ""}`}
              disabled={nextDisabled}
            >
              다음
            </button>
          ) : (
            <button
              onClick={createCriteria}
              className="rounded-lg bg-blue-600 px-4 py-2 text-sm font-extrabold text-white"
            >
              기준 생성
            </button>
          )}
        </div>
      </div>
    );
  };

  return (
    <div className="min-h-screen bg-slate-50 text-slate-900">
      {/* Top Bar */}
      <div className="sticky top-0 z-20 bg-white border-b border-slate-200">
        <div className="h-14 px-4 flex items-center gap-4">
          <div className="flex items-center gap-2 min-w-[180px]">
            <div className="h-8 w-8 rounded-lg bg-slate-900" />
            <div className="font-extrabold tracking-tight">Alpeta <span className="text-blue-600">X</span></div>
            <div className="text-xs text-slate-400 ml-2 hidden lg:block">Copyright slogan text area</div>
          </div>

          <div className="flex-1 flex items-center justify-center">
            <div className="w-full max-w-[560px]">
              <div className="relative">
                <input
                  className="w-full rounded-full border border-slate-200 bg-slate-50 px-4 py-2 text-sm outline-none focus:ring-2 focus:ring-slate-200"
                  placeholder="Search 사용자, 기능"
                />
                <div className="absolute right-3 top-1/2 -translate-y-1/2 text-slate-400 text-sm">⌕</div>
              </div>
            </div>
          </div>

          <div className="flex items-center gap-2">
            <button className="h-9 w-9 rounded-full border border-slate-200 bg-white">ⓘ</button>
            <button className="h-9 w-9 rounded-full border border-slate-200 bg-white">⚙</button>
            <button className="h-9 w-9 rounded-full border border-slate-200 bg-white">⎋</button>
          </div>
        </div>

        {/* HR Tabs */}
        <div className="px-4 pb-3">
          <div className="flex items-center gap-2">
            <button className="px-4 py-2 rounded-lg bg-blue-600 text-white text-sm font-bold">근무시간 관리</button>
            <button className="px-4 py-2 rounded-lg bg-slate-100 text-slate-600 text-sm font-semibold">리포트</button>
            <button className="px-4 py-2 rounded-lg bg-slate-100 text-slate-600 text-sm font-semibold">식수관리</button>
          </div>
        </div>
      </div>

      <div className="flex">
        {/* Left Rail */}
        <div className="w-[84px] shrink-0 border-r border-slate-200 bg-white min-h-[calc(100vh-56px)]">
          <div className="py-4 flex flex-col items-center gap-3">
            {["Dashboard", "User", "Device", "Access", "FMS", "Guard", "HR"].map((t, idx) => {
              const active = t === "HR";
              return (
                <button
                  key={idx}
                  className={`w-12 h-12 rounded-2xl border flex items-center justify-center text-xs font-bold ${
                    active ? "bg-blue-600 text-white border-blue-600" : "bg-white text-slate-600 border-slate-200"
                  }`}
                >
                  ic
                </button>
              );
            })}
          </div>
        </div>

        {/* Left Submenu */}
        <div className="w-[240px] shrink-0 border-r border-slate-200 bg-white">
          <div className="p-4">
            <div className="rounded-2xl border border-slate-200 overflow-hidden">
              {["근무유형 관리", "근무일정 관리", "근무시간 관리"].map((m) => {
                const active = leftMenu === m;
                return (
                  <button
                    key={m}
                    onClick={() => setLeftMenu(m)}
                    className={`w-full flex items-center justify-between px-4 py-3 text-sm font-bold ${
                      active ? "bg-slate-50 text-slate-900" : "bg-white text-slate-700"
                    } border-b border-slate-100 last:border-b-0`}
                  >
                    <span>{m}</span>
                    <span className="text-slate-400">›</span>
                  </button>
                );
              })}
            </div>
          </div>
        </div>

        {/* Main */}
        <div className="flex-1 p-5">
          <div className="rounded-3xl border border-slate-200 bg-white p-5">
            {/* Header row */}
            <div className="flex items-center justify-between gap-3">
              <div className="text-lg font-extrabold">근무시간 관리</div>
              <button onClick={openWizard} className="rounded-lg bg-blue-600 px-4 py-2 text-sm font-extrabold text-white">
                +시간 기준 추가
              </button>
            </div>

            {/* Filter row */}
            <div className="mt-4 grid grid-cols-12 gap-3 items-end">
              <div className="col-span-12 md:col-span-3">
                <div className="text-xs font-bold text-slate-600 mb-1">근무유형</div>
                <Select value={filterType} onChange={setFilterType} options={selectOptionsType} />
              </div>
              <div className="col-span-12 md:col-span-3">
                <div className="text-xs font-bold text-slate-600 mb-1">사용 여부</div>
                <Select value={filterUse} onChange={setFilterUse} options={selectOptionsUse} />
              </div>
              <div className="col-span-12 md:col-span-6">
                <div className="text-xs font-bold text-slate-600 mb-1">검색</div>
                <Input value={q} onChange={setQ} placeholder="검색어를 입력해주세요." />
              </div>
            </div>

            {/* Content split */}
            <div className="mt-5 grid grid-cols-12 gap-4">
              {/* List */}
              <div className="col-span-12 lg:col-span-4">
                <div className="space-y-3">
                  {filtered.map((it) => (
                    <Card
                      key={it.id}
                      active={it.id === selectedId}
                      title={it.title}
                      subtitle={it.subtitle}
                      chips={it.tags}
                      use={it.use}
                      onClick={() => {
                        setSelectedId(it.id);
                        setMode("view");
                      }}
                    />
                  ))}
                  {filtered.length === 0 ? (
                    <div className="rounded-xl border border-dashed border-slate-200 bg-slate-50 p-6 text-sm text-slate-500">조건에 해당하는 기준이 없습니다.</div>
                  ) : null}
                </div>
              </div>

              {/* Detail */}
              <div className="col-span-12 lg:col-span-8">
                <div className="space-y-4">
                  <Section
                    title="기준 상세"
                    right={
                      mode === "view" ? (
                        <button onClick={() => setMode("edit")} className="rounded-lg border border-slate-200 bg-white px-3 py-2 text-sm font-bold">
                          편집
                        </button>
                      ) : (
                        <div className="flex items-center gap-2">
                          <button onClick={onCancel} className="rounded-lg border border-slate-200 bg-white px-3 py-2 text-sm font-bold">
                            취소
                          </button>
                          <button onClick={onSave} className="rounded-lg bg-blue-600 px-3 py-2 text-sm font-extrabold text-white">
                            저장
                          </button>
                        </div>
                      )
                    }
                  >
                    <div className="flex items-center gap-3 flex-wrap">
                      <Seg value={tab} setValue={setTab} items={[{ value: "기본", label: "기본" }, { value: "야간", label: "야간" }]} />
                      <div className="text-xs text-slate-500">
                        선택된 카드: <span className="font-bold text-slate-700">{selected?.title}</span>
                      </div>
                    </div>

                    <div className="mt-4">
                      <FieldRow label="기준 이름">
                        <Input value={name} onChange={setName} disabled={!canEdit} />
                      </FieldRow>
                      <FieldRow label="설명">
                        <Input value={desc} onChange={setDesc} disabled={!canEdit} />
                      </FieldRow>
                      <FieldRow label="사용 여부">
                        <Select
                          value={useStateValue}
                          onChange={setUseStateValue}
                          disabled={!canEdit}
                          options={[{ value: "사용", label: "사용" }, { value: "미사용", label: "미사용" }]}
                        />
                      </FieldRow>

                      <div className="grid grid-cols-12 gap-3">
                        <div className="col-span-12 md:col-span-6">
                          <FieldRow label="시간 산출 단위">
                            <Select
                              value={unit}
                              onChange={setUnit}
                              disabled={!canEdit}
                              options={[{ value: "1분", label: "1분" }, { value: "5분", label: "5분" }, { value: "10분", label: "10분" }]}
                            />
                          </FieldRow>
                        </div>
                        <div className="col-span-12 md:col-span-6">
                          <FieldRow label="반올림 방식">
                            <Select
                              value={rounding}
                              onChange={setRounding}
                              disabled={!canEdit}
                              options={[{ value: "버림", label: "버림" }, { value: "반올림", label: "반올림" }, { value: "올림", label: "올림" }]}
                            />
                          </FieldRow>
                        </div>
                      </div>
                    </div>
                  </Section>

                  <Section title="기본 근무">
                    <div className="grid grid-cols-12 gap-3 items-center">
                      <div className="col-span-12 md:col-span-3 text-sm font-medium text-slate-700">근무일 기준 시간</div>
                      <div className="col-span-12 md:col-span-9">
                        <Input value={workdayRange} onChange={setWorkdayRange} disabled={!canEdit} />
                      </div>
                    </div>

                    <div className="mt-4 flex items-center justify-between">
                      <div className="text-sm font-medium text-slate-700">근무 제외 시간 설정</div>
                      <Toggle checked={excludeEnabled} onChange={setExcludeEnabled} disabled={!canEdit} />
                    </div>
                    <div className="mt-3 space-y-2">
                      <Check checked={excludeOutside} onChange={setExcludeOutside} disabled={!canEdit || !excludeEnabled} label="외출 시간 근무에서 제외" />
                      <Check checked={excludeMidnight} onChange={setExcludeMidnight} disabled={!canEdit || !excludeEnabled} label="중간에 나간 시간 근무에서 제외" />
                    </div>
                  </Section>

                  <Section title="야간 근무">
                    <div className="grid grid-cols-12 gap-3">
                      <div className="col-span-12 md:col-span-6">
                        <FieldRow label="야간 시간 구간">
                          <div className="flex items-center gap-2">
                            <Input value={nightStart} onChange={setNightStart} disabled={!canEdit} />
                            <span className="text-slate-400">-</span>
                            <Input value={nightEnd} onChange={setNightEnd} disabled={!canEdit} />
                          </div>
                        </FieldRow>
                      </div>
                      <div className="col-span-12 md:col-span-6">
                        <div className="flex items-center justify-between py-2">
                          <div className="text-sm font-medium text-slate-700">익일 종료</div>
                          <Toggle checked={nightAutoEnd} onChange={setNightAutoEnd} disabled={!canEdit} />
                        </div>
                      </div>
                    </div>

                    <div className="grid grid-cols-12 gap-3 mt-2">
                      <div className="col-span-12 md:col-span-4">
                        <div className="text-xs font-bold text-slate-600 mb-1">인정 범위</div>
                        <div className="flex items-center gap-2">
                          <Input value={nightIntervalMin} onChange={setNightIntervalMin} disabled={!canEdit} />
                          <span className="text-sm text-slate-500">분</span>
                        </div>
                      </div>
                      <div className="col-span-12 md:col-span-4">
                        <div className="text-xs font-bold text-slate-600 mb-1">분 (최소)</div>
                        <div className="flex items-center gap-2">
                          <Input value={nightMin} onChange={setNightMin} disabled={!canEdit} />
                          <span className="text-sm text-slate-500">분</span>
                        </div>
                      </div>
                      <div className="col-span-12 md:col-span-4">
                        <div className="text-xs font-bold text-slate-600 mb-1">분 (최대)</div>
                        <div className="flex items-center gap-2">
                          <Input value={nightMax} onChange={setNightMax} disabled={!canEdit} />
                          <span className="text-sm text-slate-500">분</span>
                        </div>
                      </div>
                    </div>

                    <div className="mt-4 flex items-center justify-between">
                      <div className="text-sm font-medium text-slate-700">다른 근무시간에 합산</div>
                      <Toggle checked={mergeOther} onChange={setMergeOther} disabled={!canEdit} />
                    </div>
                  </Section>

                  <div className="pt-1 text-xs text-slate-500">
                    <span className="font-semibold">데모 포인트</span>: +시간 기준 추가 → Step3에서 기본 근무 고정 + 추가 선택 시 하단 설정 노출
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      {/* Wizard Modal */}
      <ModalShell open={wizardOpen} title="근무 시간 기준 만들기" onClose={closeWizard} footer={<WizardFooter />}>
        <WizardBody />
      </ModalShell>

      {/* Confirm Modal (night validation) */}
      <ModalShell
        open={confirmOpen}
        title="확인"
        onClose={() => setConfirmOpen(false)}
        footer={
          <div className="flex items-center justify-end gap-2">
            <button onClick={() => setConfirmOpen(false)} className="rounded-lg border border-slate-200 bg-white px-4 py-2 text-sm font-bold">
              닫기
            </button>
            <button
              onClick={() => {
                setConfirmOpen(false);
                // 사용자가 익일 넘김을 켜고 진행하도록 유도
                setWNightOverDay(true);
                setWizardStep(4);
              }}
              className="rounded-lg bg-blue-600 px-4 py-2 text-sm font-extrabold text-white"
            >
              익일 넘어감(+1일) 적용
            </button>
          </div>
        }
      >
        <div className="text-sm text-slate-700 break-keep">종료 시간이 시작 시간보다 빠릅니다. <span className="font-bold">[익일 넘어감(+1일)]</span>을 선택한 후 다시 시도해주세요.</div>
      </ModalShell>

      {toast ? (
        <div className={toastBase}>
          <div className="flex items-center gap-2">
            <span className={`h-2.5 w-2.5 rounded-full ${toast.type === "success" ? "bg-emerald-500" : "bg-slate-400"}`} />
            <span className="font-semibold text-slate-800">{toast.message}</span>
            <span className="text-slate-400">·</span>
            <span className="text-slate-500">프로토타입</span>
          </div>
        </div>
      ) : null}
    </div>
  );
}
