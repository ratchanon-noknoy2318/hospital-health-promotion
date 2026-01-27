# Technical Specification Framework
**Institutional Infrastructure:** Kamphaeng Phet Community Municipal Hospital  
**Document Identifier:** KPC-HIS-HEALTH-002  
**Subject:** Health Promotion Integration Service (Webhook & Flex Synthesis Engine)  
**Classification:** Internal Use Only (Confidential)  
**Revision:** 1.0.5 (2026)

---

<p align="center">
  <img src="richmenu.png" alt="Health Promotion Interface Protocol" width="550" style="border: 2px solid #1a1a1a; border-radius: 12px; box-shadow: 0 4px 12px rgba(0,0,0,0.15);">
  <br>
  <em><strong>Exhibit B:</strong> Architectural Layout of Health Promotion Service Interface (5 grid)</em>
</p>

### 2.2 Event Routing Matrix & Service Mapping

The following table delineates the systematic mapping between user-initiated keywords and their corresponding internal synthesis protocols:

| Functional Domain | Triggering Keyword Aliases | Protocol (Synthesis Handler) |
|:---|:---|:---|
| **Scheduling** | ตารางนัดหมายและการจองคิว | `getPrenatalAppointments` |
| **Education** | ความรู้คุณแม่ตั้งครรภ์, ความรู้หญิงตั้งครรภ์ | `educatePregnantWomen`, `getPregnancySymptoms` |
| **Consultation** | ติดต่อ-สอบถาม, ศูนย์ช่วยเหลือ | `getContactUS`, `getHelpCenter` |
| **Family Planning** | ความรู้เกี่ยวกับการวางแผนครอบครัว | `getContraceptiveInfo` |
| **Public Relations** | ประชาสัมพันธ์ | `communicationAndSupport` |
| **Specialized Care** | งานส่งเสริมสุขภาพแม่และเด็ก | `supportMotherChildWellbeing` |
| **Clinical Guidance** | ควรฝากเมื่อไหร่, ควรฝากครรภ์เมื่อไหร่? | `getWhenToGetCare` |
| **Institutional** | เกี่ยวกับเรา, about us, บุคลากร | `getAboutUs`, `getTeam` |
| **Information** | คำถามที่พบบ่อย | `getFaq` |

---
