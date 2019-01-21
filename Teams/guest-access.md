---
title: Microsoft Teams でのゲスト アクセス
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 11/26/2018
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
search.appverid: MET150
description: Microsoft Teams でのゲスト アクセスにより、組織内のチームは組織外の人にチームおよびチャネルへのアクセス権を付与することで、それらの人と共同作業することができるようになります。
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: b77af005130a4e3783f69c908184a8e19b44a9c5
ms.sourcegitcommit: 454ded73af5854d7b81a3b996702a6464b3fc313
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2019
ms.locfileid: "27772794"
---
<a name="guest-access-in-microsoft-teams"></a>Microsoft Teams でのゲスト アクセス
======================================

## <a name="guest-access-overview"></a>ゲスト アクセスの概要

ゲスト アクセスは、ユーザーからの要望が最も強かった機能の 1 つです。 ゲスト アクセスの機能の開発状況に付いていくための方法と、その機能に関する意見や要望を提出するための方法を、以下に示します。

- ゲスト アクセスに関して問題がある場合は、「[Microsoft Teams の既知の問題](Known-issues.md)」を確認してください。
- 今後実装される新機能や更新された機能については、「[Teams のロードマップ](https://aka.ms/teamsroadmap)」で見つけてください。
- ご要望については、「[Teams UserVoice](https://aka.ms/TeamsUserVoice)」でお知らせください。
- 下にある [コメント] セクションでお客様ご自身のエクスペリエンスを共有してください。


ゲスト アクセスにより、組織内のチームは組織外のユーザーに、1 つまたは複数のテナントでの既存のチームおよびチャネルに対するアクセス権を付与することで、それらのユーザーと共同作業することができるようになります。 Outlook、Gmail などの勤務先または通常のメール アカウントを持っているユーザーは、チーム チャット、会議、ファイルに完全なアクセス権を持つゲストとして Teams に参加することができます。

ゲスト アクセスは、Office 365 Business Premium、Office 365 Enterprise、Office 365 Education のすべてのサブスクリプションに含まれており、追加でライセンスは必要となりません。 テナントでライセンスされたユーザーごとに、5 人のゲストまでを追加することができます。 ライセンスに関する詳細については、「[Azure Active Directory B2B コラボレーションのライセンスに関するガイダンス](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance)」をご覧ください。 

ゲスト アクセスは Microsoft Teams ではテナントレベルの設定であり、既定ではオフになっています。 ゲスト アクセスは Azure AD および Office 365 のサービス制限に適用されます。

> [!NOTE]
> Exchange Online プラン 2 などの、スタンドアロンの Office 365 サブスクリプション計画のみを持っている組織内のユーザーは、Teams によって組織に属しているものと見なされるため、その同じ組織へのゲストとして招待されることはできません。 Teams を使用するこれらのユーザーの場合は、Office 365 Business Premium、Office 365 Enterprise、または Office 365 Education サブスクリプションが割り当てられる必要があります。 

## <a name="who-is-a-guest"></a>ゲストとは何ですか?

ゲストとは、従業員、学生または組織の一員ではないユーザーを指します。 ゲストは組織内での学校アカウントまたは職場アカウントを持ちません。 たとえば、ゲストにはパートナー、製造元、供給元、コンサルタントなどが含まれます。 自分の組織に属していないすべてのユーザーを Teams のゲストとして追加することができます。 これは、ビジネス アカウント (すなわち、Azure Active Directory アカウント) または、コンシューマー メール アカウント (Outlook.com、Gmail.com 他) を持つあらゆるユーザーが、チームおよびチャネルの操作や機能に完全にアクセスすることができるゲストとして、Teams に参加することができることを意味します。 (ゲストの制限事項については、「[Microsoft Teams でのゲスト アクセスを承認する](teams-dependencies.md)」をご覧ください。)Teams のすべてのゲストは、Office 365 の他の部分と同じコンプライアンスと監査による保護の対象となり、Azure AD 内で安全に管理されます。 

## <a name="why-use-guest-access"></a>ゲスト アクセスを使用する理由を教えてください。
      
ゲスト アクセスにより、Teams を使用している組織は、企業データに対する完全な制御を維持しながら、パートナーにチーム、チャネル内のドキュメント、リソース、チャット、アプリケーションへの外部アクセスを提供することができます。 Teams のすべてのゲストは、Office 365 の他の部分と同じコンプライアンスと監査による保護の対象となります。また、ゲストは Azure AD 内で安全に管理されます。  

Teams は、Office 365 グループに基づき構築されており、Office 365 グループの共有資産への新しいアクセス方法を提供します。 Teams は、グループ/チーム メンバー間の常設チャットに最適なソリューションです。 Office 365 グループは、SharePoint サイトや Power BI ダッシュボードなどの一連の共有チーム資産を利用するために、クロス アプリケーションのメンバーシップを提供し、チームが効果的かつ安全にコラボレーションできるようにするサービスです。 

## <a name="how-does-guest-access-compare-to-federation-external-access"></a>ゲスト アクセスをフェデレーション (外部アクセス) と比較するとどのようになりますか?

フェデレーションまたは外部アクセスでは、外部ユーザーは Teams または Skype for Business を使用して別の組織のユーザーと 1 対 1 のチャットや、通話を行うことができます。 フェデレーションされたユーザーはチームのリソースにアクセスすることができません。 ゲスト アクセスと比較すると、外部アクセスでは、明示的な招待なしで、(ポリシーによって許可されている場合に) 組織間にわたる通信が許可されますが、チャットおよび通話のみに制限されます。

## <a name="more-information"></a>詳細情報
    
[Microsoft Teams のサポート リソース](support-resources.md)  
[Office 365 グループのゲスト アクセス](https://support.office.com/en-us/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ) 
  
|  |  |
|---------|---------|
|Introduction to guest access (ゲスト アクセスの概要)   | <iframe width="350" height="200" src="https://www.youtube.com/embed/D8DW2Urv5y8" frameborder="0" allowfullscreen></iframe>   |
|Deep dive into Guest Access (ゲスト アクセスの詳細)   | <iframe width="350" height="200" src="https://www.youtube.com/embed/vaJRRSjBxxY" frameborder="0" allowfullscreen></iframe>   |
| Adding guests in Microsoft Teams (Microsoft Teams でのゲストの追加)   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
    

