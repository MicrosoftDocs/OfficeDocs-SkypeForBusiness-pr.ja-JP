---
title: Microsoft Teams でのゲスト アクセス
author: LaithAlShamri
ms.author: lolaj
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
ms.openlocfilehash: 8db3f5e451e9b1a68588af637f10a908f7fa5ff9
ms.sourcegitcommit: fbcd150e724456ea4521d68cf3acb351e3525e2e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2018
ms.locfileid: "26674506"
---
<a name="guest-access-in-microsoft-teams"></a>Microsoft Teams でのゲスト アクセス
======================================

## <a name="guest-access-overview"></a>ゲスト アクセスの概要

ゲスト アクセスは、お客様が、ほとんどの機能の 1 つです。 ゲスト アクセスの進展に対応し、ご意見をお聞かせする方法を以下に示します。

- ゲスト アクセスに関して問題がある場合は、「[Microsoft Teams の既知の問題](Known-issues.md)」を確認してください。
- 今後実装される新機能や更新された機能については、「[Teams のロードマップ](https://aka.ms/teamsroadmap)」で見つけてください。
- ご要望については、「[Teams UserVoice](https://aka.ms/TeamsUserVoice)」でお知らせください。
- 下にある [コメント] セクションでお客様ご自身のエクスペリエンスを共有してください。


ゲスト アクセスでは、既存のチームと、テナントの 1 つ以上のチャネルへのアクセスに付与することによって、組織外のユーザーと共同作業を行う組織でチームを許可します。 ビジネスやコンシューマー電子メール アカウントを Outlook、Gmail、またはその他のユーザーなど、すべてのユーザーは、チーム チャット、会議、およびファイルへのフル アクセスを持つチームにゲストとして参加できます。

ゲスト アクセスに含まれていない追加のライセンス要件を持つすべての Office 365 のビジネス プレミアム、Office 365 の企業、および Office 365 の教育の購読。 テナントのライセンスを受けたユーザーあたり 5 つまでの来園者を持つことができます。 ライセンスの詳細については、 [Azure Active Directory B2B コラボレーションのライセンス ガイド](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance)を参照してください。 

ゲスト アクセスは Microsoft Teams ではテナントレベルの設定であり、既定ではオフになっています。 Azure AD は、ゲスト アクセス、Office 365 サービスの制限です。

> [!NOTE]
> チームがこれらのユーザーに同じ組織に属していると見なされるために、組織にゲストとして Exchange オンライン計画 2 などだけでは、スタンドアロンの Office 365 サブスクリプション プランを持つ、組織内のユーザーを招待できません。 チームを使用するこれらのユーザーに割り当てる必要があります、Office 365 のビジネス プレミアム、Office 365 の企業、または Office 365 の教育のサブスクリプション。 

## <a name="who-is-a-guest"></a>ゲストは誰ですか。

ゲストとは、従業員、学生または組織の一員ではないユーザーを指します。 ゲストは組織内での学校アカウントまたは職場アカウントを持ちません。 たとえば、ゲストにはパートナー、製造元、供給元、コンサルタントなどが含まれます。 チームでは、ゲストとしては、すべての組織の一部ではないユーザーを追加できます。 これは、ビジネス アカウント (つまり、Azure Active Directory) または (Outlook.com、Gmail.com またはその他のユーザー) とコンシューマーの電子メール アカウントを持つユーザーがチームへのフル アクセスを持つ、チームのゲストとして参加できるし、チャネルが発生したことを意味します。 (確認できるのゲストの制限では、[マイクロソフトのチームでのゲスト アクセスを許可](teams-dependencies.md)します。)来園者はチームでは、同じコンプライアンスと監査の保護として、Office 365 の残りの部分についてし、Azure AD 内で安全に管理することができます。 来園者はチームでは、同じコンプライアンスと監査の保護として、Office 365 の残りの部分についてし、Azure AD 内で安全に管理することができます。

## <a name="why-use-guest-access"></a>ゲスト アクセスを使用する理由
      
ゲスト アクセス権を持つチームを使用している組織は、独自の企業データを完全に制御を維持しながらチーム、チャネル、リソース、チャット、および、パートナーでは、アプリケーション内のドキュメントへの外部アクセスを提供できます。 来園者は Azure AD 内で安全に管理できるし、同じコンプライアンスと監査の保護として、Office 365 の残りの部分は、来園者はチームで対応します。  

チームでは、Office 365 のグループが適用され、Office 365 のグループの共有アセットにアクセスするための新しい方法が用意されています。 Teams は、グループ/チーム メンバー間の常設チャットに最適なソリューションです。 Office 365 グループは、SharePoint サイトや Power BI ダッシュボードなどの一連の共有チーム資産を利用するために、クロス アプリケーションのメンバーシップを提供し、チームが効果的かつ安全にコラボレーションできるようにするサービスです。 

## <a name="how-does-guest-access-compare-to-federation-external-access"></a>ゲスト アクセスはフェデレーション (外部アクセス) にどのような比較をするでしょうか。

フェデレーションまたは外部からのアクセスでは、外部ユーザーですることが 1 対 1 のチャットと通話別の組織内のユーザーとチームまたは Skype のいずれかを使用してビジネスの。 フェデレーション ユーザーは、チーム リソースにアクセスできません。 ゲスト アクセスと比べると、外部からのアクセスは、明示的な招待状のない組織の間の通信 (ポリシーで許可されている) 場合が、チャットにのみに限定されます。

## <a name="more-information"></a>詳細情報
    
[Microsoft Teams のサポート リソース](support-resources.md)  
[Office 365 のグループでのゲスト アクセス](https://support.office.com/en-us/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ) 
  
|  |  |
|---------|---------|
|ゲスト アクセスの概要   | <iframe width="350" height="200" src="https://www.youtube.com/embed/D8DW2Urv5y8" frameborder="0" allowfullscreen></iframe>   |
|ゲスト アクセスを掘り下げ   | <iframe width="350" height="200" src="https://www.youtube.com/embed/vaJRRSjBxxY" frameborder="0" allowfullscreen></iframe>   |
| マイクロソフトのチームで、来園者を追加します。   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
    

