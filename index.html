import { useState, useEffect, useRef } from "react";

// ==================== MOCK DATA ====================
const MOCK_USERS = {
  admin: { id: "u1", name: "អ្នកគ្រប់គ្រង", role: "admin", email: "admin@school.edu.kh", avatar: "A" },
  teacher: { id: "u2", name: "គ្រូ សុខា", role: "teacher", email: "sokha@school.edu.kh", avatar: "ស" },
  student: { id: "u3", name: "សិស្ស វិចិត្រ", role: "student", email: "vichit@school.edu.kh", avatar: "វ", class: "ទី ១០A", grade: 10 },
};

const INITIAL_STUDENTS = [
  { id: "s1", name: "វិចិត្រ សុភ័គ", code: "2024-001", class: "ទី ១០A", grade: 10, gender: "male", contact: "012-345-678" },
  { id: "s2", name: "ស្រីណា ចន្ទ", code: "2024-002", class: "ទី ១០A", grade: 10, gender: "female", contact: "015-678-901" },
  { id: "s3", name: "បញ្ញា ខេម", code: "2024-003", class: "ទី ១០A", grade: 10, gender: "male", contact: "016-234-567" },
  { id: "s4", name: "លក្ខណ៍ សាន", code: "2024-004", class: "ទី ១០A", grade: 10, gender: "female", contact: "017-890-123" },
  { id: "s5", name: "ដារ៉ា ហ៊ន", code: "2024-005", class: "ទី ១០A", grade: 10, gender: "male", contact: "010-456-789" },
  { id: "s6", name: "ចន្ទបូ ម៉ារ", code: "2024-006", class: "ទី ១១B", grade: 11, gender: "female", contact: "011-321-654" },
  { id: "s7", name: "វឌ្ឍន៍ ពេជ្រ", code: "2024-007", class: "ទី ១១B", grade: 11, gender: "male", contact: "092-147-258" },
  { id: "s8", name: "រតនា ស", code: "2024-008", class: "ទី ១២C", grade: 12, gender: "female", contact: "093-369-741" },
];

const INITIAL_EXAMS = [
  { id: "e1", title: "ប្រឡងខែ មករា", type: "monthly", period: "monthly", class: "ទី ១០A", date: "2025-01-15", totalMarks: 100, subject: "Computer Science" },
  { id: "e2", title: "ប្រឡងខែ កុម្ភៈ", type: "monthly", period: "monthly", class: "ទី ១០A", date: "2025-02-20", totalMarks: 100, subject: "Computer Science" },
  { id: "e3", title: "ប្រឡងឆមាស ១", type: "annual", period: "semester1", class: "ទី ១០A", date: "2025-03-10", totalMarks: 150, subject: "Computer Science" },
  { id: "e4", title: "ប្រឡងខែ មករា", type: "monthly", period: "monthly", class: "ទី ១១B", date: "2025-01-18", totalMarks: 100, subject: "Computer Science" },
];

const INITIAL_SCORES = [
  { id: "sc1", studentId: "s1", examId: "e1", score: 85, isGraded: true },
  { id: "sc2", studentId: "s2", examId: "e1", score: 92, isGraded: true },
  { id: "sc3", studentId: "s3", examId: "e1", score: 78, isGraded: true },
  { id: "sc4", studentId: "s4", examId: "e1", score: 95, isGraded: true },
  { id: "sc5", studentId: "s5", examId: "e1", score: 71, isGraded: true },
  { id: "sc6", studentId: "s1", examId: "e2", score: 88, isGraded: true },
  { id: "sc7", studentId: "s2", examId: "e2", score: 90, isGraded: true },
  { id: "sc8", studentId: "s3", examId: "e2", score: 82, isGraded: true },
  { id: "sc9", studentId: "s4", examId: "e2", score: 97, isGraded: true },
  { id: "sc10", studentId: "s5", examId: "e2", score: 74, isGraded: true },
  { id: "sc11", studentId: "s1", examId: "e3", score: 128, isGraded: true },
  { id: "sc12", studentId: "s2", examId: "e3", score: 138, isGraded: true },
  { id: "sc13", studentId: "s3", examId: "e3", score: 115, isGraded: true },
  { id: "sc14", studentId: "s4", examId: "e3", score: 142, isGraded: true },
  { id: "sc15", studentId: "s5", examId: "e3", score: 108, isGraded: true },
];

const CLASSES = ["ទី ១០A", "ទី ១០B", "ទី ១១A", "ទី ១១B", "ទី ១២A", "ទី ១២B", "ទី ១២C"];

// ==================== HELPERS ====================
const gradeLabel = (score, total) => {
  const pct = (score / total) * 100;
  if (pct >= 90) return { label: "A", color: "#1D9E75" };
  if (pct >= 80) return { label: "B", color: "#185FA5" };
  if (pct >= 70) return { label: "C", color: "#BA7517" };
  if (pct >= 60) return { label: "D", color: "#D85A30" };
  return { label: "F", color: "#E24B4A" };
};

const getRank = (studentId, examId, scores) => {
  const examScores = scores.filter(s => s.examId === examId && s.isGraded).sort((a, b) => b.score - a.score);
  return examScores.findIndex(s => s.studentId === studentId) + 1;
};

// ==================== COMPONENTS ====================

function Avatar({ user, size = 36 }) {
  const colors = { admin: "#534AB7", teacher: "#0F6E56", student: "#993C1D" };
  return (
    <div style={{
      width: size, height: size, borderRadius: "50%",
      background: colors[user.role] || "#5F5E5A",
      display: "flex", alignItems: "center", justifyContent: "center",
      color: "#fff", fontSize: size * 0.4, fontWeight: 600, flexShrink: 0
    }}>
      {user.avatar}
    </div>
  );
}

function Badge({ text, type = "info" }) {
  const styles = {
    info: { bg: "#E6F1FB", color: "#185FA5" },
    success: { bg: "#E1F5EE", color: "#0F6E56" },
    warning: { bg: "#FAEEDA", color: "#854F0B" },
    danger: { bg: "#FCEBEB", color: "#A32D2D" },
    purple: { bg: "#EEEDFE", color: "#3C3489" },
    gray: { bg: "#F1EFE8", color: "#5F5E5A" },
  };
  const s = styles[type] || styles.info;
  return (
    <span style={{
      background: s.bg, color: s.color,
      padding: "2px 10px", borderRadius: 20, fontSize: 12, fontWeight: 500,
      display: "inline-block", whiteSpace: "nowrap"
    }}>{text}</span>
  );
}

function StatCard({ label, value, sub, color = "#185FA5", icon }) {
  return (
    <div style={{
      background: "var(--color-background-secondary,#f8f8f6)", borderRadius: 12,
      padding: "16px 20px", flex: 1, minWidth: 140,
      border: "1px solid var(--color-border-tertiary,rgba(0,0,0,0.1))"
    }}>
      <div style={{ fontSize: 11, color: "var(--color-text-secondary,#888)", marginBottom: 6, textTransform: "uppercase", letterSpacing: 1 }}>{icon} {label}</div>
      <div style={{ fontSize: 28, fontWeight: 600, color }}>{value}</div>
      {sub && <div style={{ fontSize: 12, color: "var(--color-text-secondary,#888)", marginTop: 4 }}>{sub}</div>}
    </div>
  );
}

function Modal({ title, onClose, children, width = 520 }) {
  return (
    <div style={{
      position: "fixed", inset: 0, zIndex: 1000,
      background: "rgba(0,0,0,0.45)", display: "flex", alignItems: "center", justifyContent: "center"
    }} onClick={e => e.target === e.currentTarget && onClose()}>
      <div style={{
        background: "var(--color-background-primary,#fff)", borderRadius: 16,
        width: Math.min(width, window.innerWidth - 32), maxHeight: "90vh", overflowY: "auto",
        boxShadow: "0 8px 40px rgba(0,0,0,0.18)"
      }}>
        <div style={{ display: "flex", alignItems: "center", justifyContent: "space-between", padding: "20px 24px 0" }}>
          <h3 style={{ margin: 0, fontSize: 18, fontWeight: 600, color: "var(--color-text-primary,#222)" }}>{title}</h3>
          <button onClick={onClose} style={{ background: "none", border: "none", cursor: "pointer", fontSize: 22, color: "var(--color-text-secondary,#888)", lineHeight: 1, padding: 4 }}>×</button>
        </div>
        <div style={{ padding: 24 }}>{children}</div>
      </div>
    </div>
  );
}

function Input({ label, ...props }) {
  return (
    <div style={{ marginBottom: 16 }}>
      {label && <label style={{ display: "block", fontSize: 13, fontWeight: 500, marginBottom: 6, color: "var(--color-text-primary,#222)" }}>{label}</label>}
      <input {...props} style={{
        width: "100%", boxSizing: "border-box",
        padding: "10px 12px", borderRadius: 8, fontSize: 14,
        border: "1.5px solid var(--color-border-secondary,rgba(0,0,0,0.2))",
        background: "var(--color-background-primary,#fff)",
        color: "var(--color-text-primary,#222)", outline: "none",
        ...props.style
      }} />
    </div>
  );
}

function Select({ label, children, ...props }) {
  return (
    <div style={{ marginBottom: 16 }}>
      {label && <label style={{ display: "block", fontSize: 13, fontWeight: 500, marginBottom: 6, color: "var(--color-text-primary,#222)" }}>{label}</label>}
      <select {...props} style={{
        width: "100%", padding: "10px 12px", borderRadius: 8, fontSize: 14,
        border: "1.5px solid var(--color-border-secondary,rgba(0,0,0,0.2))",
        background: "var(--color-background-primary,#fff)",
        color: "var(--color-text-primary,#222)", outline: "none", cursor: "pointer",
        ...props.style
      }}>{children}</select>
    </div>
  );
}

function Btn({ children, onClick, variant = "primary", small, disabled, style: s = {} }) {
  const base = {
    cursor: disabled ? "not-allowed" : "pointer",
    border: "none", borderRadius: 8, fontWeight: 500, fontSize: small ? 13 : 14,
    padding: small ? "6px 14px" : "10px 20px",
    transition: "opacity 0.15s", opacity: disabled ? 0.5 : 1,
    ...s
  };
  const variants = {
    primary: { background: "#185FA5", color: "#fff" },
    success: { background: "#0F6E56", color: "#fff" },
    danger: { background: "#A32D2D", color: "#fff" },
    ghost: { background: "transparent", color: "var(--color-text-primary,#222)", border: "1.5px solid var(--color-border-secondary,rgba(0,0,0,0.2))" },
    purple: { background: "#534AB7", color: "#fff" },
  };
  return (
    <button style={{ ...base, ...variants[variant] }} onClick={disabled ? undefined : onClick}>{children}</button>
  );
}

// ==================== LOGIN PAGE ====================
function LoginPage({ onLogin }) {
  const [role, setRole] = useState("teacher");
  const [loading, setLoading] = useState(false);

  const handleLogin = () => {
    setLoading(true);
    setTimeout(() => { onLogin(MOCK_USERS[role]); setLoading(false); }, 800);
  };

  return (
    <div style={{
      minHeight: "100vh", display: "flex", alignItems: "center", justifyContent: "center",
      background: "linear-gradient(135deg, #0F2942 0%, #185FA5 60%, #1D9E75 100%)",
      fontFamily: "system-ui, sans-serif"
    }}>
      <div style={{
        background: "rgba(255,255,255,0.97)", borderRadius: 20, padding: 40,
        width: 380, boxShadow: "0 20px 60px rgba(0,0,0,0.25)"
      }}>
        <div style={{ textAlign: "center", marginBottom: 32 }}>
          <div style={{ fontSize: 40, marginBottom: 8 }}>🏫</div>
          <h1 style={{ margin: 0, fontSize: 22, fontWeight: 700, color: "#0F2942" }}>ប្រព័ន្ធគ្រប់គ្រង</h1>
          <p style={{ margin: "6px 0 0", fontSize: 14, color: "#888" }}>ថ្នាក់រៀនកុំព្យូទ័រ · Computer Class</p>
        </div>

        <div style={{ marginBottom: 20 }}>
          <label style={{ fontSize: 13, fontWeight: 500, display: "block", marginBottom: 8, color: "#333" }}>ជ្រើសតួអង្គ (Demo)</label>
          <div style={{ display: "flex", gap: 8 }}>
            {[["admin", "👤 Admin"], ["teacher", "🎓 គ្រូ"], ["student", "📚 សិស្ស"]].map(([r, l]) => (
              <button key={r} onClick={() => setRole(r)} style={{
                flex: 1, padding: "10px 6px", borderRadius: 10, fontSize: 13, cursor: "pointer", fontWeight: 500,
                border: role === r ? "2px solid #185FA5" : "1.5px solid #ddd",
                background: role === r ? "#E6F1FB" : "#f8f8f6",
                color: role === r ? "#185FA5" : "#555", transition: "all 0.15s"
              }}>{l}</button>
            ))}
          </div>
        </div>

        <Btn onClick={handleLogin} disabled={loading} style={{ width: "100%", padding: "13px", fontSize: 15, borderRadius: 10 }}>
          {loading ? "កំពុង Login..." : "ចូលប្រព័ន្ធ →"}
        </Btn>

        <p style={{ textAlign: "center", fontSize: 12, color: "#bbb", marginTop: 20 }}>
          Demo Version · CompSchool EduSys v1.0
        </p>
      </div>
    </div>
  );
}

// ==================== SIDEBAR ====================
function Sidebar({ user, activePage, setActivePage, collapsed, setCollapsed }) {
  const adminNav = [
    { id: "dashboard", icon: "📊", label: "Dashboard" },
    { id: "students", icon: "👥", label: "សិស្ស" },
    { id: "exams", icon: "📝", label: "ការប្រឡង" },
    { id: "scores", icon: "🏆", label: "ពិន្ទុ" },
    { id: "reports", icon: "📄", label: "របាយការណ៍" },
    { id: "settings", icon: "⚙️", label: "ការកំណត់" },
  ];
  const teacherNav = [
    { id: "dashboard", icon: "📊", label: "Dashboard" },
    { id: "students", icon: "👥", label: "សិស្ស" },
    { id: "exams", icon: "📝", label: "ការប្រឡង" },
    { id: "scores", icon: "🏆", label: "ដាក់ពិន្ទុ" },
    { id: "reports", icon: "📄", label: "របាយការណ៍" },
  ];
  const studentNav = [
    { id: "dashboard", icon: "📊", label: "Dashboard" },
    { id: "myexams", icon: "📝", label: "ការប្រឡងរបស់ខ្ញុំ" },
    { id: "myscores", icon: "🏆", label: "ពិន្ទុរបស់ខ្ញុំ" },
  ];
  const nav = user.role === "admin" ? adminNav : user.role === "teacher" ? teacherNav : studentNav;
  const roleColors = { admin: "#534AB7", teacher: "#185FA5", student: "#0F6E56" };
  const c = roleColors[user.role];

  return (
    <div style={{
      width: collapsed ? 64 : 220, flexShrink: 0, transition: "width 0.2s",
      background: "#0F2942", display: "flex", flexDirection: "column",
      height: "100vh", position: "sticky", top: 0, overflow: "hidden"
    }}>
      {/* Logo */}
      <div style={{
        padding: collapsed ? "20px 0" : "20px 16px", display: "flex",
        alignItems: "center", gap: 10, borderBottom: "1px solid rgba(255,255,255,0.1)",
        cursor: "pointer", userSelect: "none"
      }} onClick={() => setCollapsed(!collapsed)}>
        <span style={{ fontSize: 24, flexShrink: 0, marginLeft: collapsed ? 20 : 0 }}>🏫</span>
        {!collapsed && <div>
          <div style={{ color: "#fff", fontWeight: 700, fontSize: 13 }}>CompSchool</div>
          <div style={{ color: "rgba(255,255,255,0.5)", fontSize: 11 }}>EduSys v1.0</div>
        </div>}
      </div>

      {/* User info */}
      {!collapsed && (
        <div style={{ padding: "16px", borderBottom: "1px solid rgba(255,255,255,0.08)" }}>
          <div style={{ display: "flex", alignItems: "center", gap: 10 }}>
            <Avatar user={user} size={36} />
            <div style={{ minWidth: 0 }}>
              <div style={{ color: "#fff", fontSize: 13, fontWeight: 500, overflow: "hidden", textOverflow: "ellipsis", whiteSpace: "nowrap" }}>{user.name}</div>
              <Badge text={user.role === "admin" ? "Admin" : user.role === "teacher" ? "គ្រូ" : "សិស្ស"} type="purple" />
            </div>
          </div>
        </div>
      )}

      {/* Nav */}
      <nav style={{ flex: 1, padding: "12px 0", overflowY: "auto" }}>
        {nav.map(item => (
          <div key={item.id} onClick={() => setActivePage(item.id)} style={{
            display: "flex", alignItems: "center", gap: 12,
            padding: collapsed ? "12px 0" : "11px 16px", cursor: "pointer",
            background: activePage === item.id ? `${c}33` : "transparent",
            borderLeft: activePage === item.id ? `3px solid ${c}` : "3px solid transparent",
            transition: "all 0.15s", justifyContent: collapsed ? "center" : "flex-start"
          }}>
            <span style={{ fontSize: 18, flexShrink: 0 }}>{item.icon}</span>
            {!collapsed && <span style={{ color: activePage === item.id ? "#fff" : "rgba(255,255,255,0.65)", fontSize: 14, fontWeight: activePage === item.id ? 600 : 400 }}>{item.label}</span>}
          </div>
        ))}
      </nav>

      {/* Logout */}
      <div style={{ padding: collapsed ? "16px 0" : "16px", borderTop: "1px solid rgba(255,255,255,0.1)" }}>
        <div style={{ display: "flex", alignItems: "center", gap: 10, cursor: "pointer", justifyContent: collapsed ? "center" : "flex-start" }}>
          <span style={{ fontSize: 18 }}>🚪</span>
          {!collapsed && <span style={{ color: "rgba(255,255,255,0.5)", fontSize: 13 }}>ចាកចេញ</span>}
        </div>
      </div>
    </div>
  );
}

// ==================== DASHBOARD ====================
function Dashboard({ user, students, exams, scores }) {
  const classStudents = user.role === "student" ? [] : students;
  const classExams = exams;
  const totalScores = scores.filter(s => s.isGraded);
  const avg = totalScores.length > 0 ? (totalScores.reduce((a, b) => a + b.score, 0) / totalScores.length).toFixed(1) : 0;

  const gradeDistribution = [
    { label: "A (90-100%)", count: 0, color: "#1D9E75" },
    { label: "B (80-89%)", count: 0, color: "#185FA5" },
    { label: "C (70-79%)", count: 0, color: "#BA7517" },
    { label: "D (60-69%)", count: 0, color: "#D85A30" },
    { label: "F (<60%)", count: 0, color: "#E24B4A" },
  ];
  scores.forEach(sc => {
    const exam = exams.find(e => e.id === sc.examId);
    if (!exam) return;
    const pct = (sc.score / exam.totalMarks) * 100;
    if (pct >= 90) gradeDistribution[0].count++;
    else if (pct >= 80) gradeDistribution[1].count++;
    else if (pct >= 70) gradeDistribution[2].count++;
    else if (pct >= 60) gradeDistribution[3].count++;
    else gradeDistribution[4].count++;
  });
  const maxGradeCount = Math.max(...gradeDistribution.map(g => g.count), 1);

  const recentExams = [...exams].sort((a, b) => new Date(b.date) - new Date(a.date)).slice(0, 4);

  return (
    <div>
      <h2 style={{ margin: "0 0 6px", fontSize: 22, fontWeight: 700, color: "var(--color-text-primary,#222)" }}>
        {user.role === "student" ? `សួស្តី, ${user.name}! 👋` : "Dashboard ទូទៅ"}
      </h2>
      <p style={{ margin: "0 0 24px", color: "var(--color-text-secondary,#888)", fontSize: 14 }}>
        ឆ្នាំសិក្សា ២០២៤–២០២៥ · មុខវិជ្ជា: Computer Science
      </p>

      {/* Stats */}
      <div style={{ display: "flex", gap: 16, flexWrap: "wrap", marginBottom: 28 }}>
        {user.role !== "student" && <StatCard label="សិស្សសរុប" value={students.length} sub={`${students.filter(s => s.grade <= 10).length} ទី១០ · ${students.filter(s => s.grade === 11).length} ទី១១ · ${students.filter(s => s.grade === 12).length} ទី១២`} color="#534AB7" icon="👥" />}
        <StatCard label="ការប្រឡងសរុប" value={classExams.length} sub={`${classExams.filter(e => e.type === "monthly").length} ប្រចាំខែ · ${classExams.filter(e => e.type === "annual").length} ប្រចាំឆ្នាំ`} color="#185FA5" icon="📝" />
        <StatCard label="មធ្យមភាគ" value={`${avg}%`} sub="ពិន្ទុជាមធ្យម" color="#0F6E56" icon="📊" />
        {user.role !== "student" && <StatCard label="ពិន្ទុបានដាក់" value={totalScores.length} sub="ធាតុចូលទាំងអស់" color="#BA7517" icon="✅" />}
      </div>

      <div style={{ display: "grid", gridTemplateColumns: "1fr 1fr", gap: 20 }}>
        {/* Grade distribution */}
        <div style={{ background: "var(--color-background-secondary,#f8f8f6)", borderRadius: 14, padding: 20, border: "1px solid var(--color-border-tertiary,rgba(0,0,0,0.08))" }}>
          <h3 style={{ margin: "0 0 18px", fontSize: 15, fontWeight: 600 }}>📈 ការចែកចាយពិន្ទុ</h3>
          {gradeDistribution.map(g => (
            <div key={g.label} style={{ marginBottom: 10 }}>
              <div style={{ display: "flex", justifyContent: "space-between", fontSize: 12, marginBottom: 4 }}>
                <span style={{ color: "var(--color-text-secondary,#888)" }}>{g.label}</span>
                <span style={{ fontWeight: 600, color: g.color }}>{g.count}</span>
              </div>
              <div style={{ height: 8, background: "var(--color-border-tertiary,rgba(0,0,0,0.08))", borderRadius: 4, overflow: "hidden" }}>
                <div style={{ height: "100%", width: `${(g.count / maxGradeCount) * 100}%`, background: g.color, borderRadius: 4, transition: "width 0.5s" }} />
              </div>
            </div>
          ))}
        </div>

        {/* Recent exams */}
        <div style={{ background: "var(--color-background-secondary,#f8f8f6)", borderRadius: 14, padding: 20, border: "1px solid var(--color-border-tertiary,rgba(0,0,0,0.08))" }}>
          <h3 style={{ margin: "0 0 18px", fontSize: 15, fontWeight: 600 }}>📋 ការប្រឡងថ្មីៗ</h3>
          {recentExams.map(exam => (
            <div key={exam.id} style={{ display: "flex", alignItems: "center", justifyContent: "space-between", padding: "10px 0", borderBottom: "1px solid var(--color-border-tertiary,rgba(0,0,0,0.06))" }}>
              <div>
                <div style={{ fontSize: 13, fontWeight: 500, color: "var(--color-text-primary,#222)" }}>{exam.title}</div>
                <div style={{ fontSize: 12, color: "var(--color-text-secondary,#888)" }}>{exam.class} · {exam.date}</div>
              </div>
              <Badge text={exam.type === "monthly" ? "ប្រចាំខែ" : "ប្រចាំឆ្នាំ"} type={exam.type === "monthly" ? "info" : "purple"} />
            </div>
          ))}
        </div>
      </div>
    </div>
  );
}

// ==================== STUDENTS PAGE ====================
function StudentsPage({ user, students, setStudents }) {
  const [search, setSearch] = useState("");
  const [filterClass, setFilterClass] = useState("all");
  const [showModal, setShowModal] = useState(false);
  const [editStudent, setEditStudent] = useState(null);
  const [form, setForm] = useState({ name: "", code: "", class: "ទី ១០A", gender: "male", contact: "" });

  const filtered = students.filter(s => {
    const matchSearch = s.name.includes(search) || s.code.includes(search);
    const matchClass = filterClass === "all" || s.class === filterClass;
    return matchSearch && matchClass;
  });

  const openAdd = () => { setEditStudent(null); setForm({ name: "", code: "", class: "ទី ១០A", gender: "male", contact: "" }); setShowModal(true); };
  const openEdit = (s) => { setEditStudent(s); setForm({ name: s.name, code: s.code, class: s.class, gender: s.gender, contact: s.contact }); setShowModal(true); };
  const handleSave = () => {
    if (!form.name || !form.code) return;
    if (editStudent) {
      setStudents(students.map(s => s.id === editStudent.id ? { ...s, ...form, grade: parseInt(form.class.match(/\d+/)?.[0] || 10) } : s));
    } else {
      const grade = parseInt(form.class.match(/\d+/)?.[0] || 10);
      setStudents([...students, { id: `s${Date.now()}`, ...form, grade }]);
    }
    setShowModal(false);
  };
  const handleDelete = (id) => setStudents(students.filter(s => s.id !== id));

  const canEdit = user.role !== "student";

  return (
    <div>
      <div style={{ display: "flex", justifyContent: "space-between", alignItems: "center", marginBottom: 20 }}>
        <div>
          <h2 style={{ margin: 0, fontSize: 22, fontWeight: 700 }}>👥 គ្រប់គ្រងសិស្ស</h2>
          <p style={{ margin: "4px 0 0", color: "var(--color-text-secondary,#888)", fontSize: 14 }}>សិស្សសរុប: {filtered.length} នាក់</p>
        </div>
        {canEdit && <Btn onClick={openAdd} variant="primary">+ បន្ថែមសិស្ស</Btn>}
      </div>

      <div style={{ display: "flex", gap: 12, marginBottom: 20 }}>
        <input
          placeholder="🔍 ស្វែងរកឈ្មោះ ឬលេខកូដ..."
          value={search} onChange={e => setSearch(e.target.value)}
          style={{ flex: 1, padding: "10px 14px", borderRadius: 8, border: "1.5px solid var(--color-border-secondary,rgba(0,0,0,0.15))", background: "var(--color-background-secondary,#f8f8f6)", fontSize: 14, color: "var(--color-text-primary,#222)", outline: "none" }}
        />
        <select value={filterClass} onChange={e => setFilterClass(e.target.value)} style={{ padding: "10px 14px", borderRadius: 8, border: "1.5px solid var(--color-border-secondary,rgba(0,0,0,0.15))", background: "var(--color-background-secondary,#f8f8f6)", fontSize: 14, color: "var(--color-text-primary,#222)", outline: "none", cursor: "pointer" }}>
          <option value="all">ថ្នាក់ទាំងអស់</option>
          {CLASSES.map(c => <option key={c} value={c}>{c}</option>)}
        </select>
      </div>

      <div style={{ background: "var(--color-background-secondary,#f8f8f6)", borderRadius: 14, overflow: "hidden", border: "1px solid var(--color-border-tertiary,rgba(0,0,0,0.08))" }}>
        <table style={{ width: "100%", borderCollapse: "collapse" }}>
          <thead>
            <tr style={{ background: "var(--color-background-tertiary,#f0efea)" }}>
              {["#", "ឈ្មោះ", "លេខកូដ", "ថ្នាក់", "ភេទ", "ទំនាក់ទំនង", ""].map(h => (
                <th key={h} style={{ padding: "12px 16px", textAlign: "left", fontSize: 13, fontWeight: 600, color: "var(--color-text-secondary,#666)", whiteSpace: "nowrap" }}>{h}</th>
              ))}
            </tr>
          </thead>
          <tbody>
            {filtered.map((s, i) => (
              <tr key={s.id} style={{ borderTop: "1px solid var(--color-border-tertiary,rgba(0,0,0,0.06))", transition: "background 0.1s" }}
                onMouseEnter={e => e.currentTarget.style.background = "var(--color-background-tertiary,#f5f4f0)"}
                onMouseLeave={e => e.currentTarget.style.background = ""}>
                <td style={{ padding: "12px 16px", fontSize: 13, color: "var(--color-text-secondary,#888)" }}>{i + 1}</td>
                <td style={{ padding: "12px 16px" }}>
                  <div style={{ display: "flex", alignItems: "center", gap: 10 }}>
                    <div style={{ width: 32, height: 32, borderRadius: "50%", background: s.gender === "female" ? "#F4C0D1" : "#B5D4F4", display: "flex", alignItems: "center", justifyContent: "center", fontSize: 14 }}>
                      {s.gender === "female" ? "👩" : "👦"}
                    </div>
                    <span style={{ fontWeight: 500, fontSize: 14 }}>{s.name}</span>
                  </div>
                </td>
                <td style={{ padding: "12px 16px", fontSize: 13, fontFamily: "monospace", color: "#185FA5" }}>{s.code}</td>
                <td style={{ padding: "12px 16px" }}><Badge text={s.class} type="info" /></td>
                <td style={{ padding: "12px 16px" }}><Badge text={s.gender === "female" ? "ស្រី" : "ប្រុស"} type={s.gender === "female" ? "warning" : "gray"} /></td>
                <td style={{ padding: "12px 16px", fontSize: 13, color: "var(--color-text-secondary,#888)" }}>{s.contact}</td>
                <td style={{ padding: "12px 16px" }}>
                  {canEdit && (
                    <div style={{ display: "flex", gap: 8 }}>
                      <Btn small variant="ghost" onClick={() => openEdit(s)}>✏️</Btn>
                      <Btn small variant="danger" onClick={() => handleDelete(s.id)}>🗑️</Btn>
                    </div>
                  )}
                </td>
              </tr>
            ))}
          </tbody>
        </table>
        {filtered.length === 0 && <div style={{ padding: 40, textAlign: "center", color: "var(--color-text-secondary,#888)" }}>រកមិនឃើញសិស្ស</div>}
      </div>

      {showModal && (
        <Modal title={editStudent ? "កែប្រែសិស្ស" : "បន្ថែមសិស្សថ្មី"} onClose={() => setShowModal(false)}>
          <Input label="ឈ្មោះ" placeholder="ឧ. វិចិត្រ សុភ័គ" value={form.name} onChange={e => setForm({ ...form, name: e.target.value })} />
          <Input label="លេខកូដ" placeholder="ឧ. 2024-001" value={form.code} onChange={e => setForm({ ...form, code: e.target.value })} />
          <Select label="ថ្នាក់" value={form.class} onChange={e => setForm({ ...form, class: e.target.value })}>
            {CLASSES.map(c => <option key={c} value={c}>{c}</option>)}
          </Select>
          <Select label="ភេទ" value={form.gender} onChange={e => setForm({ ...form, gender: e.target.value })}>
            <option value="male">ប្រុស</option>
            <option value="female">ស្រី</option>
          </Select>
          <Input label="ទំនាក់ទំនងមាតាបិតា" placeholder="ឧ. 012-345-678" value={form.contact} onChange={e => setForm({ ...form, contact: e.target.value })} />
          <div style={{ display: "flex", gap: 10, justifyContent: "flex-end" }}>
            <Btn variant="ghost" onClick={() => setShowModal(false)}>បោះបង់</Btn>
            <Btn variant="primary" onClick={handleSave}>{editStudent ? "រក្សាទុក" : "បន្ថែម"}</Btn>
          </div>
        </Modal>
      )}
    </div>
  );
}

// ==================== EXAMS PAGE ====================
function ExamsPage({ user, exams, setExams }) {
  const [showModal, setShowModal] = useState(false);
  const [form, setForm] = useState({ title: "", type: "monthly", period: "monthly", class: "ទី ១០A", date: "", totalMarks: 100, subject: "Computer Science" });

  const handleSave = () => {
    if (!form.title || !form.date) return;
    setExams([...exams, { id: `e${Date.now()}`, ...form, totalMarks: parseInt(form.totalMarks) }]);
    setShowModal(false);
    setForm({ title: "", type: "monthly", period: "monthly", class: "ទី ១០A", date: "", totalMarks: 100, subject: "Computer Science" });
  };

  const canCreate = user.role !== "student";

  return (
    <div>
      <div style={{ display: "flex", justifyContent: "space-between", alignItems: "center", marginBottom: 20 }}>
        <div>
          <h2 style={{ margin: 0, fontSize: 22, fontWeight: 700 }}>📝 ការប្រឡង</h2>
          <p style={{ margin: "4px 0 0", color: "var(--color-text-secondary,#888)", fontSize: 14 }}>ការប្រឡងទាំងអស់: {exams.length}</p>
        </div>
        {canCreate && <Btn onClick={() => setShowModal(true)} variant="primary">+ បង្កើតការប្រឡង</Btn>}
      </div>

      <div style={{ display: "grid", gridTemplateColumns: "repeat(auto-fill, minmax(300px, 1fr))", gap: 16 }}>
        {exams.map(exam => {
          const typeColor = exam.type === "monthly" ? "#185FA5" : "#534AB7";
          const typeBg = exam.type === "monthly" ? "#E6F1FB" : "#EEEDFE";
          return (
            <div key={exam.id} style={{
              background: "var(--color-background-secondary,#f8f8f6)", borderRadius: 14,
              padding: 20, border: "1px solid var(--color-border-tertiary,rgba(0,0,0,0.08))",
              transition: "transform 0.15s, box-shadow 0.15s", cursor: "default"
            }}
              onMouseEnter={e => { e.currentTarget.style.transform = "translateY(-2px)"; e.currentTarget.style.boxShadow = "0 4px 20px rgba(0,0,0,0.1)"; }}
              onMouseLeave={e => { e.currentTarget.style.transform = ""; e.currentTarget.style.boxShadow = ""; }}>
              <div style={{ display: "flex", justifyContent: "space-between", alignItems: "flex-start", marginBottom: 12 }}>
                <span style={{ fontSize: 28 }}>{exam.type === "monthly" ? "📅" : "🎯"}</span>
                <span style={{ background: typeBg, color: typeColor, padding: "4px 12px", borderRadius: 20, fontSize: 12, fontWeight: 600 }}>
                  {exam.type === "monthly" ? "ប្រចាំខែ" : "ប្រចាំឆ្នាំ"}
                </span>
              </div>
              <h3 style={{ margin: "0 0 8px", fontSize: 16, fontWeight: 700, color: "var(--color-text-primary,#222)" }}>{exam.title}</h3>
              <div style={{ fontSize: 13, color: "var(--color-text-secondary,#888)", marginBottom: 4 }}>📚 {exam.subject}</div>
              <div style={{ fontSize: 13, color: "var(--color-text-secondary,#888)", marginBottom: 4 }}>🏫 ថ្នាក់: {exam.class}</div>
              <div style={{ fontSize: 13, color: "var(--color-text-secondary,#888)", marginBottom: 4 }}>📆 ថ្ងៃ: {exam.date}</div>
              <div style={{ fontSize: 13, fontWeight: 600, color: "#185FA5" }}>💯 ពិន្ទុ: {exam.totalMarks}</div>
            </div>
          );
        })}
      </div>

      {showModal && (
        <Modal title="បង្កើតការប្រឡងថ្មី" onClose={() => setShowModal(false)}>
          <Input label="ចំណងជើងការប្រឡង" placeholder="ឧ. ប្រឡងខែ មករា" value={form.title} onChange={e => setForm({ ...form, title: e.target.value })} />
          <Select label="ប្រភេទ" value={form.type} onChange={e => setForm({ ...form, type: e.target.value })}>
            <option value="monthly">ប្រឡងប្រចាំខែ</option>
            <option value="annual">ប្រឡងប្រចាំឆ្នាំ / ឆមាស</option>
          </Select>
          <Select label="ថ្នាក់" value={form.class} onChange={e => setForm({ ...form, class: e.target.value })}>
            {CLASSES.map(c => <option key={c} value={c}>{c}</option>)}
          </Select>
          <Input label="ថ្ងៃប្រឡង" type="date" value={form.date} onChange={e => setForm({ ...form, date: e.target.value })} />
          <Input label="ពិន្ទុសរុប" type="number" value={form.totalMarks} onChange={e => setForm({ ...form, totalMarks: e.target.value })} />
          <div style={{ display: "flex", gap: 10, justifyContent: "flex-end" }}>
            <Btn variant="ghost" onClick={() => setShowModal(false)}>បោះបង់</Btn>
            <Btn variant="primary" onClick={handleSave}>បង្កើត</Btn>
          </div>
        </Modal>
      )}
    </div>
  );
}

// ==================== SCORES PAGE ====================
function ScoresPage({ user, students, exams, scores, setScores }) {
  const [selectedExam, setSelectedExam] = useState(exams[0]?.id || "");
  const [editScores, setEditScores] = useState({});
  const [saved, setSaved] = useState(false);

  const exam = exams.find(e => e.id === selectedExam);
  const examStudents = exam ? students.filter(s => s.class === exam.class) : [];

  const getScore = (studentId) => {
    const override = editScores[studentId];
    if (override !== undefined) return override;
    return scores.find(s => s.studentId === studentId && s.examId === selectedExam)?.score ?? "";
  };

  const handleSave = () => {
    const updated = [...scores];
    Object.entries(editScores).forEach(([studentId, score]) => {
      const existing = updated.findIndex(s => s.studentId === studentId && s.examId === selectedExam);
      if (existing >= 0) updated[existing] = { ...updated[existing], score: parseFloat(score), isGraded: true };
      else updated.push({ id: `sc${Date.now()}_${studentId}`, studentId, examId: selectedExam, score: parseFloat(score), isGraded: true });
    });
    setScores(updated);
    setEditScores({});
    setSaved(true);
    setTimeout(() => setSaved(false), 2000);
  };

  const canEdit = user.role !== "student";

  return (
    <div>
      <div style={{ display: "flex", justifyContent: "space-between", alignItems: "center", marginBottom: 20 }}>
        <div>
          <h2 style={{ margin: 0, fontSize: 22, fontWeight: 700 }}>🏆 ការដាក់ & មើលពិន្ទុ</h2>
          <p style={{ margin: "4px 0 0", color: "var(--color-text-secondary,#888)", fontSize: 14 }}>ជ្រើសការប្រឡង ហើយបញ្ចូលពិន្ទុ</p>
        </div>
        {saved && <div style={{ background: "#E1F5EE", color: "#0F6E56", padding: "8px 16px", borderRadius: 8, fontWeight: 600 }}>✅ រក្សាទុករួចហើយ!</div>}
      </div>

      <div style={{ marginBottom: 20 }}>
        <Select label="ជ្រើសការប្រឡង" value={selectedExam} onChange={e => { setSelectedExam(e.target.value); setEditScores({}); }}>
          {exams.map(e => <option key={e.id} value={e.id}>{e.title} — {e.class}</option>)}
        </Select>
      </div>

      {exam && (
        <>
          <div style={{ background: "#E6F1FB", borderRadius: 10, padding: "12px 16px", marginBottom: 20, display: "flex", gap: 24, flexWrap: "wrap" }}>
            <span style={{ fontSize: 13, color: "#185FA5" }}>📝 {exam.title}</span>
            <span style={{ fontSize: 13, color: "#185FA5" }}>🏫 {exam.class}</span>
            <span style={{ fontSize: 13, color: "#185FA5" }}>📆 {exam.date}</span>
            <span style={{ fontSize: 13, color: "#185FA5" }}>💯 ពិន្ទុ Max: {exam.totalMarks}</span>
          </div>

          <div style={{ background: "var(--color-background-secondary,#f8f8f6)", borderRadius: 14, overflow: "hidden", border: "1px solid var(--color-border-tertiary,rgba(0,0,0,0.08))" }}>
            <table style={{ width: "100%", borderCollapse: "collapse" }}>
              <thead>
                <tr style={{ background: "var(--color-background-tertiary,#f0efea)" }}>
                  <th style={{ padding: "12px 16px", textAlign: "left", fontSize: 13, fontWeight: 600, color: "var(--color-text-secondary,#666)" }}>#</th>
                  <th style={{ padding: "12px 16px", textAlign: "left", fontSize: 13, fontWeight: 600, color: "var(--color-text-secondary,#666)" }}>ឈ្មោះ</th>
                  <th style={{ padding: "12px 16px", textAlign: "left", fontSize: 13, fontWeight: 600, color: "var(--color-text-secondary,#666)" }}>ពិន្ទុ</th>
                  <th style={{ padding: "12px 16px", textAlign: "left", fontSize: 13, fontWeight: 600, color: "var(--color-text-secondary,#666)" }}>ភាគរយ</th>
                  <th style={{ padding: "12px 16px", textAlign: "left", fontSize: 13, fontWeight: 600, color: "var(--color-text-secondary,#666)" }}>ចំណាត់ថ្នាក់</th>
                  <th style={{ padding: "12px 16px", textAlign: "left", fontSize: 13, fontWeight: 600, color: "var(--color-text-secondary,#666)" }}>លទ្ធផល</th>
                </tr>
              </thead>
              <tbody>
                {examStudents.map((s, i) => {
                  const rawScore = getScore(s.id);
                  const numScore = rawScore !== "" ? parseFloat(rawScore) : null;
                  const pct = numScore !== null ? ((numScore / exam.totalMarks) * 100).toFixed(1) : "—";
                  const gr = numScore !== null ? gradeLabel(numScore, exam.totalMarks) : null;
                  const rank = numScore !== null ? getRank(s.id, selectedExam, scores) : null;
                  return (
                    <tr key={s.id} style={{ borderTop: "1px solid var(--color-border-tertiary,rgba(0,0,0,0.06))" }}>
                      <td style={{ padding: "12px 16px", fontSize: 13, color: "var(--color-text-secondary,#888)" }}>{i + 1}</td>
                      <td style={{ padding: "12px 16px", fontWeight: 500, fontSize: 14 }}>{s.name}</td>
                      <td style={{ padding: "12px 16px" }}>
                        {canEdit ? (
                          <input
                            type="number" min="0" max={exam.totalMarks}
                            value={rawScore}
                            onChange={e => setEditScores({ ...editScores, [s.id]: e.target.value })}
                            style={{ width: 80, padding: "6px 10px", borderRadius: 6, border: "1.5px solid var(--color-border-secondary,rgba(0,0,0,0.2))", fontSize: 14, fontWeight: 600, textAlign: "center", background: "var(--color-background-primary,#fff)", color: "var(--color-text-primary,#222)", outline: "none" }}
                          />
                        ) : (
                          <span style={{ fontWeight: 700, fontSize: 16, color: gr?.color || "#888" }}>{numScore ?? "—"}</span>
                        )}
                      </td>
                      <td style={{ padding: "12px 16px", fontSize: 14, fontWeight: 600, color: gr?.color || "var(--color-text-secondary,#888)" }}>{pct}{numScore !== null ? "%" : ""}</td>
                      <td style={{ padding: "12px 16px" }}>{rank ? <span style={{ fontWeight: 700, color: rank === 1 ? "#BA7517" : "#888" }}>{rank === 1 ? "🥇" : rank === 2 ? "🥈" : rank === 3 ? "🥉" : `#${rank}`}</span> : "—"}</td>
                      <td style={{ padding: "12px 16px" }}>
                        {gr ? (
                          <span style={{ background: gr.color + "22", color: gr.color, padding: "4px 12px", borderRadius: 20, fontSize: 13, fontWeight: 700 }}>{gr.label}</span>
                        ) : "—"}
                      </td>
                    </tr>
                  );
                })}
              </tbody>
            </table>
          </div>

          {canEdit && (
            <div style={{ marginTop: 16, display: "flex", justifyContent: "flex-end" }}>
              <Btn variant="success" onClick={handleSave}>💾 រក្សាទុកពិន្ទុ</Btn>
            </div>
          )}
        </>
      )}
    </div>
  );
}

// ==================== REPORTS PAGE ====================
function ReportsPage({ user, students, exams, scores }) {
  const [filterClass, setFilterClass] = useState("ទី ១០A");
  const [filterExam, setFilterExam] = useState("all");

  const classStudents = students.filter(s => s.class === filterClass);
  const classExams = exams.filter(e => e.class === filterClass);

  const getStudentAvg = (studentId) => {
    const examFilter = filterExam === "all" ? classExams : classExams.filter(e => e.id === filterExam);
    const studentScores = scores.filter(s => s.studentId === studentId && examFilter.some(e => e.id === s.examId) && s.isGraded);
    if (studentScores.length === 0) return null;
    const total = studentScores.reduce((acc, sc) => {
      const exam = exams.find(e => e.id === sc.examId);
      return acc + (exam ? (sc.score / exam.totalMarks) * 100 : 0);
    }, 0);
    return (total / studentScores.length).toFixed(1);
  };

  const reportData = classStudents.map(s => {
    const avg = getStudentAvg(s.id);
    const gr = avg !== null ? gradeLabel(parseFloat(avg), 100) : null;
    return { ...s, avg, gr };
  }).sort((a, b) => (parseFloat(b.avg) || 0) - (parseFloat(a.avg) || 0));

  const classAvg = reportData.filter(s => s.avg !== null).reduce((acc, s, _, arr) => acc + parseFloat(s.avg) / arr.length, 0).toFixed(1);

  return (
    <div>
      <div style={{ display: "flex", justifyContent: "space-between", alignItems: "center", marginBottom: 20 }}>
        <div>
          <h2 style={{ margin: 0, fontSize: 22, fontWeight: 700 }}>📄 របាយការណ៍</h2>
          <p style={{ margin: "4px 0 0", color: "var(--color-text-secondary,#888)", fontSize: 14 }}>លទ្ធផលសិក្សា · Academic Report</p>
        </div>
        <Btn variant="success" onClick={() => alert("📥 Export PDF — Feature នេះត្រូវការ Backend!\n\nក្នុង Production: ប្រើ PDFKit ឬ Puppeteer generate PDF ហើយ download.")}>
          📥 Export PDF
        </Btn>
      </div>

      <div style={{ display: "flex", gap: 12, marginBottom: 20 }}>
        <Select label="" value={filterClass} onChange={e => setFilterClass(e.target.value)} style={{ marginBottom: 0 }}>
          {CLASSES.map(c => <option key={c} value={c}>{c}</option>)}
        </Select>
        <Select label="" value={filterExam} onChange={e => setFilterExam(e.target.value)} style={{ marginBottom: 0 }}>
          <option value="all">ការប្រឡងទាំងអស់</option>
          {classExams.map(e => <option key={e.id} value={e.id}>{e.title}</option>)}
        </Select>
      </div>

      {/* Summary */}
      <div style={{ display: "flex", gap: 16, marginBottom: 20, flexWrap: "wrap" }}>
        <StatCard label="សិស្សសរុប" value={classStudents.length} color="#534AB7" icon="👥" />
        <StatCard label="មធ្យមភាគ" value={`${classAvg}%`} color="#0F6E56" icon="📊" />
        <StatCard label="ក្រឡាឆ្លងកាត់" value={reportData.filter(s => parseFloat(s.avg) >= 50).length} sub="≥ 50%" color="#185FA5" icon="✅" />
        <StatCard label="ត្រូវរៀនសើរ" value={reportData.filter(s => s.avg !== null && parseFloat(s.avg) < 50).length} sub="< 50%" color="#E24B4A" icon="⚠️" />
      </div>

      {/* Report Table */}
      <div style={{ background: "var(--color-background-secondary,#f8f8f6)", borderRadius: 14, overflow: "hidden", border: "1px solid var(--color-border-tertiary,rgba(0,0,0,0.08))" }}>
        <div style={{ padding: "16px 20px", borderBottom: "1px solid var(--color-border-tertiary,rgba(0,0,0,0.08))", display: "flex", justifyContent: "space-between", alignItems: "center" }}>
          <span style={{ fontWeight: 700, fontSize: 15 }}>📊 លទ្ធផលពិន្ទុ — {filterClass}</span>
          <span style={{ fontSize: 13, color: "var(--color-text-secondary,#888)" }}>ឆ្នាំសិក្សា ២០២៤–២០២៥</span>
        </div>
        <table style={{ width: "100%", borderCollapse: "collapse" }}>
          <thead>
            <tr style={{ background: "var(--color-background-tertiary,#f0efea)" }}>
              {["ចំណាត់", "ឈ្មោះ", "លេខកូដ", ...classExams.slice(0, 3).map(e => e.title.substring(0, 10) + "..."), "មធ្យម", "លទ្ធផល"].map(h => (
                <th key={h} style={{ padding: "12px 14px", textAlign: "left", fontSize: 12, fontWeight: 600, color: "var(--color-text-secondary,#666)", whiteSpace: "nowrap" }}>{h}</th>
              ))}
            </tr>
          </thead>
          <tbody>
            {reportData.map((s, i) => {
              const examScores = classExams.slice(0, 3).map(exam => {
                const sc = scores.find(sc => sc.studentId === s.id && sc.examId === exam.id);
                return sc ? `${sc.score}/${exam.totalMarks}` : "—";
              });
              return (
                <tr key={s.id} style={{ borderTop: "1px solid var(--color-border-tertiary,rgba(0,0,0,0.06))" }}>
                  <td style={{ padding: "11px 14px", fontWeight: 700, fontSize: 16, color: i === 0 ? "#BA7517" : i === 1 ? "#888" : i === 2 ? "#D85A30" : "var(--color-text-secondary,#888)" }}>
                    {i === 0 ? "🥇" : i === 1 ? "🥈" : i === 2 ? "🥉" : `${i + 1}`}
                  </td>
                  <td style={{ padding: "11px 14px", fontWeight: 500, fontSize: 14 }}>{s.name}</td>
                  <td style={{ padding: "11px 14px", fontSize: 12, fontFamily: "monospace", color: "#185FA5" }}>{s.code}</td>
                  {examScores.map((sc, j) => (
                    <td key={j} style={{ padding: "11px 14px", fontSize: 13, fontWeight: 500, color: sc === "—" ? "#bbb" : "var(--color-text-primary,#222)" }}>{sc}</td>
                  ))}
                  <td style={{ padding: "11px 14px", fontWeight: 700, fontSize: 15, color: s.gr?.color || "#888" }}>
                    {s.avg !== null ? `${s.avg}%` : "—"}
                  </td>
                  <td style={{ padding: "11px 14px" }}>
                    {s.gr ? (
                      <span style={{ background: s.gr.color + "22", color: s.gr.color, padding: "4px 12px", borderRadius: 20, fontSize: 13, fontWeight: 700 }}>{s.gr.label}</span>
                    ) : "—"}
                  </td>
                </tr>
              );
            })}
          </tbody>
        </table>
      </div>
    </div>
  );
}

// ==================== MY SCORES (STUDENT) ====================
function MyScoresPage({ user, exams, scores }) {
  const myScores = scores.filter(s => s.studentId === user.id);
  return (
    <div>
      <h2 style={{ margin: "0 0 6px", fontSize: 22, fontWeight: 700 }}>🏆 ពិន្ទុរបស់ខ្ញុំ</h2>
      <p style={{ margin: "0 0 24px", color: "var(--color-text-secondary,#888)", fontSize: 14 }}>{user.class} · {user.name}</p>
      <div style={{ display: "grid", gridTemplateColumns: "repeat(auto-fill, minmax(280px, 1fr))", gap: 16 }}>
        {myScores.map(sc => {
          const exam = exams.find(e => e.id === sc.examId);
          if (!exam) return null;
          const pct = ((sc.score / exam.totalMarks) * 100).toFixed(1);
          const gr = gradeLabel(sc.score, exam.totalMarks);
          return (
            <div key={sc.id} style={{ background: "var(--color-background-secondary,#f8f8f6)", borderRadius: 14, padding: 20, border: `2px solid ${gr.color}33` }}>
              <div style={{ display: "flex", justifyContent: "space-between", alignItems: "flex-start" }}>
                <div>
                  <div style={{ fontWeight: 700, fontSize: 15, marginBottom: 4 }}>{exam.title}</div>
                  <div style={{ fontSize: 13, color: "var(--color-text-secondary,#888)" }}>{exam.date} · {exam.class}</div>
                </div>
                <span style={{ fontSize: 36, fontWeight: 800, color: gr.color }}>{gr.label}</span>
              </div>
              <div style={{ marginTop: 16, display: "flex", gap: 16 }}>
                <div style={{ textAlign: "center" }}>
                  <div style={{ fontSize: 24, fontWeight: 700, color: gr.color }}>{sc.score}</div>
                  <div style={{ fontSize: 12, color: "#888" }}>ពិន្ទុ</div>
                </div>
                <div style={{ textAlign: "center" }}>
                  <div style={{ fontSize: 24, fontWeight: 700, color: gr.color }}>{pct}%</div>
                  <div style={{ fontSize: 12, color: "#888" }}>ភាគរយ</div>
                </div>
                <div style={{ textAlign: "center" }}>
                  <div style={{ fontSize: 24, fontWeight: 700, color: "#BA7517" }}>#{getRank(user.id, sc.examId, scores) || "—"}</div>
                  <div style={{ fontSize: 12, color: "#888" }}>ចំណាត់</div>
                </div>
              </div>
            </div>
          );
        })}
        {myScores.length === 0 && <div style={{ color: "var(--color-text-secondary,#888)", padding: 24 }}>មិនទាន់មានពិន្ទុ</div>}
      </div>
    </div>
  );
}

// ==================== SETTINGS ====================
function SettingsPage({ user }) {
  return (
    <div>
      <h2 style={{ margin: "0 0 6px", fontSize: 22, fontWeight: 700 }}>⚙️ ការកំណត់</h2>
      <p style={{ margin: "0 0 24px", color: "var(--color-text-secondary,#888)", fontSize: 14 }}>System Configuration</p>
      <div style={{ display: "grid", gridTemplateColumns: "1fr 1fr", gap: 16 }}>
        {[
          { icon: "🏫", title: "ព័ត៌មានសាលា", desc: "ឈ្មោះ, អាសយដ្ឋាន, ទំនាក់ទំនង" },
          { icon: "📅", title: "ឆ្នាំសិក្សា", desc: "គ្រប់គ្រងឆ្នាំ ២០២៤–២០២៥" },
          { icon: "👥", title: "គណនី User", desc: "Admin, Teacher, Student" },
          { icon: "📊", title: "ការកំណត់ Grade", desc: "A, B, C, D, F Thresholds" },
          { icon: "📧", title: "Email Notifications", desc: "ផ្ញើរបាយការណ៍ to Parents" },
          { icon: "💾", title: "Backup ទិន្នន័យ", desc: "Export & Import Database" },
        ].map(item => (
          <div key={item.title} style={{
            background: "var(--color-background-secondary,#f8f8f6)", borderRadius: 14,
            padding: 20, border: "1px solid var(--color-border-tertiary,rgba(0,0,0,0.08))",
            cursor: "pointer", transition: "transform 0.15s"
          }}
            onMouseEnter={e => e.currentTarget.style.transform = "translateY(-2px)"}
            onMouseLeave={e => e.currentTarget.style.transform = ""}>
            <div style={{ fontSize: 28, marginBottom: 8 }}>{item.icon}</div>
            <div style={{ fontWeight: 600, fontSize: 15, marginBottom: 4 }}>{item.title}</div>
            <div style={{ fontSize: 13, color: "var(--color-text-secondary,#888)" }}>{item.desc}</div>
          </div>
        ))}
      </div>
    </div>
  );
}

// ==================== MAIN APP ====================
export default function App() {
  const [user, setUser] = useState(null);
  const [activePage, setActivePage] = useState("dashboard");
  const [collapsed, setCollapsed] = useState(false);
  const [students, setStudents] = useState(INITIAL_STUDENTS);
  const [exams, setExams] = useState(INITIAL_EXAMS);
  const [scores, setScores] = useState(INITIAL_SCORES);

  if (!user) return <LoginPage onLogin={(u) => { setUser(u); setActivePage("dashboard"); }} />;

  const renderPage = () => {
    const props = { user, students, setStudents, exams, setExams, scores, setScores };
    switch (activePage) {
      case "dashboard": return <Dashboard {...props} />;
      case "students": return <StudentsPage {...props} />;
      case "exams": return <ExamsPage {...props} />;
      case "scores": return <ScoresPage {...props} />;
      case "myexams": return <ExamsPage {...props} />;
      case "myscores": return <MyScoresPage {...props} />;
      case "reports": return <ReportsPage {...props} />;
      case "settings": return <SettingsPage user={user} />;
      default: return <Dashboard {...props} />;
    }
  };

  return (
    <div style={{ display: "flex", minHeight: "100vh", fontFamily: "system-ui, -apple-system, sans-serif", background: "var(--color-background-tertiary,#f5f4f0)" }}>
      <Sidebar user={user} activePage={activePage} setActivePage={setActivePage} collapsed={collapsed} setCollapsed={setCollapsed} />
      <main style={{ flex: 1, padding: 28, overflowY: "auto", minHeight: "100vh" }}>
        {renderPage()}
      </main>
    </div>
  );
}
