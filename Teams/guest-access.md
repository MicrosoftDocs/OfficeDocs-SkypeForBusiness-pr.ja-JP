---
title: Microsoft Teams でのゲスト アクセス
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
audience: admin
search.appverid: MET150
description: Microsoft Teams でのゲスト アクセスにより、組織内のチームは組織外の人にチームおよびチャネルへのアクセス権を付与することで、それらの人と共同作業することができるようになります。
localization_priority: Priority
f1keywords: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ad8b75e244efa0d28709d6c5ff225f1e6676200a
ms.sourcegitcommit: ed7439d03e37c9c0184daf5215a68c5492932a83
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "38290857"
---
<a name="guest-access-in-microsoft-teams"></a>Microsoft Teams でのゲスト アクセス
======================================

ゲスト アクセスを使用すると、組織外の個々のユーザーを Microsoft Teams のチームとチャネルに追加できます。 

外部アクセス (フェデレーション) とゲスト アクセスを比較する (および使用するアクセスを決定する) には、「[Teams の他の組織のユーザーと通信する](communicate-with-users-from-other-organizations.md)」をご覧ください。

組織でゲスト アクセスをオンにする準備ができたら、「[ゲスト アクセスのチェックリスト](guest-access-checklist.md)」から始めます。

## <a name="guest-access-overview"></a>ゲスト アクセスの概要

ゲスト アクセスにより、組織内のチームは組織外の人に Teams の既存のチームおよびチャネルへのアクセス権を付与することで、それらの人と共同作業することができるようになります。 Outlook、Gmail などの勤務先または通常のメール アカウントを持っている全てのユーザーは、チーム チャット、会議、ファイルにフル アクセス権を持つゲストとして Teams に参加することができます。 Teams の管理者は、ゲストがチームで使用できる (使用できない) 機能を制御します、「[ゲスト アクセスの管理](manage-guests.md)」をご覧ください。

ゲスト アクセスは Teams の組織全体の設定であり、既定ではオフになっています。 ゲスト アクセスは Azure AD および Office 365 サービスの制限の対象になります。


> [!IMPORTANT]
> ゲスト ユーザーは、共存アップグレード モードの Teams の組織全体の設定に従います。 これは変更できません。

## <a name="licensing-for-guest-access"></a>ゲスト アクセスのライセンス

ゲスト アクセスは、Office 365 Business Premium、Office 365 Enterprise、Office 365 Education のすべてのサブスクリプションに含まれています。 追加の Office 365 ライセンスは不要です。 Teams では追加することができるゲストの数に制限はありません。 ただし、テナントに追加することができるゲストの合計数は、ご利用の Azure AD ライセンスによって許可されるものに基づきます。通常はライセンス ユーザーごとに 5 人です。 詳細については、「[Azure AD B2B コラボレーションのライセンス](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)」に関するページを参照してください。


> [!NOTE]
> Exchange Online プラン 2 などのスタンドアロン Office 365 サブスクリプションプランのみを持っている組織内のユーザーは、Teams によって組織に属しているものと見なされるため、その同じ組織へのゲストとして招待されることはできません。 Teams を使用するこれらのユーザーの場合は、Office 365 Business Premium、Office 365 Enterprise、または Office 365 Education サブスクリプションが割り当てられる必要があります。 

## <a name="who-is-a-guest"></a>ゲストとは何ですか?

ゲストとは、従業員、学生または組織の一員ではないユーザーを指します。 ゲストは組織内での学校アカウントまたは職場アカウントを持ちません。 たとえば、ゲストにはパートナー、製造元、供給元、コンサルタントなどが含まれます。 自分の組織に属していないユーザーを Teams のゲストとして追加することができます。 これは、ビジネス アカウント (すなわち、Azure Active Directory アカウント) または通常のメール アカウント (Outlook.com、Gmail.com、他) を持つすべてのユーザーが、チームとチャネルの操作や機能にフル アクセスできるゲストとして、Teams に参加できることを意味します。

ゲストができることとできないことの詳細については、「[Microsoft Teams でゲスト アクセスを許可する](teams-dependencies.md)」をご覧ください。 または、[チーム メンバーとゲスト機能の比較](guest-experience.md#comparison-of-team-member-and-guest-capabilities)表をご覧ください。 

最後に、Teams のすべてのゲストは、その他の Office 365 と同じコンプライアンスと監査保護の対象になり、Azure AD 内で安全に管理されます。

## <a name="why-use-guest-access"></a>ゲスト アクセスを使用する理由を教えてください。

ゲスト アクセスにより、Teams を使用している組織は、企業データに対する完全な制御を維持しながら、パートナーにチーム、チャネル内のドキュメント、リソース、チャット、アプリケーションへのアクセスを提供することができます。 Teams のすべてのゲストは、Office 365 と同様のコンプライアンスと監査による保護の対象となります。また、ゲストは Azure AD 内で安全に管理されます。  

## <a name="understand-the-limitations-for-guests"></a>ゲストに対する制限事項を理解する

ゲスト エクスペリエンスでは、デザインによる制限があります。問題ではないものを修正しようとしないために、必ずゲスト エクスペリエンスを理解してください。たとえば、Microsoft Teams のゲストが利用できない一部の機能を以下にリストします。

- OneDrive for Business
- Teams 外部のユーザーの検索
- カレンダー、予約済みの会議、会議の詳細
- PSTN
- 組織図
- チームの作成または修正
- チームの参照
- 個人対個人のチャットへのファイルのアップロード
- ゲストは、ユーザーの完全なメール ID が分かっていれば、引き続き (チーム外の) ユーザーを検索することができます。 これを防ぐために、IT 管理者はゲストを自分の仮想 GAL に制限することができる[範囲指定ディレクトリ検索](teams-scoped-directory-search.md)などのパターンを使用することができます。
- 現在、Teams は、[Azure B2B で定義](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)されている状態 1 および状態 2 のゲスト ユーザーのみをサポートします。

ゲストが Teams でできることとできないことの完全なリストについては、「[チーム メンバーとゲスト機能の比較](guest-experience.md#comparison-of-team-member-and-guest-capabilities)」表をご覧ください。 Office 365 レベルでのゲスト アクセスの詳細については、「[Office 365 グループへのゲストの追加](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)」をご覧ください。

## <a name="how-does-external-access-federation-compare-to-guest-access"></a>外部アクセス (フェデレーション) とゲスト アクセスの違いを教えてください。

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a>詳細情報

[ビジネス製品についてサポートに問い合わせる - 管理者ヘルプ](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)  
[Office 365 グループのゲスト アクセス](https://support.office.com/en-us/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ) 
  
