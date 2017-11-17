---
title: "チームにゲストを追加する"
author: LaithAlShamri
ms.author: laal
manager: lolaj
ms.date: 10/23/2017
ms.topic: article
ms.service: msteams
description: "組織に新しいゲスト ユーザーを追加するために管理者が利用できる Microsoft Teams デスクトップ、Web クライアント、Azure Active Directory B2B コラボレーション ポータルなどのツールについて説明します。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 7764b05a3c3e945e505800ddf30372a2438236a6
ms.sourcegitcommit: 4a396557d51c7fb246144cd682bcf5e6a2c823be
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/11/2017
---
<a name="add-a-guest-to-a-team"></a>チームにゲストを追加する
=====================

Azure Active Directory に対応する電子メール アドレス、または Office 365 の職場または学校アカウントを持つユーザーのみをゲスト ユーザーとして追加できます。


管理者として、複数の方法で組織に新しいゲスト ユーザーを追加できます。 
- チームの所有者であるグローバル管理者は、Microsoft Teams デスクトップまたは Web クライアントのいずれかを使用してチームにゲストを追加できます。
- Azure Active Directory B2B コラボレーションを使用して組織にゲストを追加します。 Azure Active Directory B2B コラボレーションを使用すると、グローバル管理者は、2000 行以下のカンマ区切り (CSV) ファイルを B2B コラボレーション ポータルにアップロードすることで、複数の外部ユーザーを招待、承認できます。 詳細については、「[Azure Active Directory B2B コラボレーション](https://go.microsoft.com/fwlink/p/?linkid=826383)」をご覧ください



Azure Active Directory B2B コラボレーションでは、組織は B2B ユーザーに対して条件付きアクセスと多要素認証 (MFA) ポリシーを適用できます。 このポリシーは、フルタイムの従業員や組織のメンバーに対して有効にするのと同じ方法で、テナント レベル、アプリ レベルまたは個々のユーザー レベルで適用できます。 こうしたポリシーはリソース組織で実施します。 詳細については、「[B2B コラボレーション ユーザーの条件付きアクセス](https://go.microsoft.com/fwlink/?linkid=857454)」をご覧ください。 個別にゲスト ユーザーを拒否することはできません。



Azure Active Directory B2B、Office 365 グループまたは SharePoint Online を介してすでに追加しているゲスト ユーザーはすぐに利用できます。 Office 365 管理者またはチーム所有者は所有するチームにこのゲストを追加できます。 チームが Office 365 グループにすでに追加されており、ゲストがそのグループに追加される場合、そのゲストはチームにアクセスできます。 Office 365 グループを介してゲストを追加すると、そのゲストへの招待状メールは生成されません。そのため、チームの他のユーザーがそのゲストに通知する必要があります。

> [!NOTE]
> ゲストにも [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) と [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) のサービスの制限が適用されます。



ゲストの追加は、Azure Active Directory または Office 365 セキュリティ &amp; コンプライアンス センターで追跡できます。 Microsoft Teams でのゲストの追加は監査され、「Added member to group (グループにメンバーを追加しました)」という Azure AD グループ管理アクティビティとして記録されます。 詳細については、「[B2B コラボレーション ユーザーの監査およびレポート](https://go.microsoft.com/fwlink/p/?linkid=858884)」と「[Office 365 のセキュリティ センター &amp; コンプライアンス センターで監査ログを検索する](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)」をご覧ください。

