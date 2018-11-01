---
title: Microsoft Teams でのゲスト アクセス
author: LaithAlShamri
ms.author: laal
manager: serdars
ms.date: 10/31/2017
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
search.appverid: MET150
description: Microsoft Teams でのゲスト アクセスにより、組織内のチームは組織外の人にチームおよびチャネルへのアクセス権を付与することで、それらの人と共同作業することができるようになります。
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4d13a48856aae71634ed6588a714d578416ed594
ms.sourcegitcommit: 6d30cfdd8c8b8908d4e4f278c39fd22062f4a888
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2018
ms.locfileid: "25890557"
---
<a name="guest-access-in-microsoft-teams"></a>Microsoft Teams でのゲスト アクセス
======================================

ゲスト アクセスは Teams での新機能です。 これは、ユーザーからの要望が最も強かった機能の 1 つです。 Microsoft では、継続してこの機能を強化する作業に取り組んでいます。 ゲスト アクセスの機能の開発状況に付いていくための方法と、その機能に関する意見や要望を提出するための方法を、以下に示します。

- ゲスト アクセスに関して問題がある場合は、「[Microsoft Teams の既知の問題](Known-issues.md)」を確認してください。
- 今後実装される新機能や更新された機能については、「[Teams のロードマップ](https://aka.ms/teamsroadmap)」で見つけてください。
- ご要望については、「[Teams UserVoice](https://aka.ms/TeamsUserVoice)」でお知らせください。
- 下にある [コメント] セクションでお客様ご自身のエクスペリエンスを共有してください。


Microsoft Teams でのゲスト アクセスにより、組織内のチームは組織外の人にチームおよびチャネルへのアクセス権を付与することで、それらの人と共同作業することができるようになります。 

ビジネスやコンシューマー電子メール アカウントを Outlook、Gmail、またはその他のユーザーなど、すべてのユーザーは、チーム チャット、会議、およびファイルへのフル アクセスを持つチームにゲストとして参加できます。

ゲスト アクセスは、Office 365 Business Premium、Office 365 Enterprise、Office 365 Education のすべてのサブスクリプションに含まれています。 追加の Office 365 ライセンスは不要です。 ゲスト アクセスは Microsoft Teams ではテナントレベルの設定であり、既定ではオフになっています。


## <a name="what-is-a-guest"></a>ゲストとは何ですか?

ゲストとは、従業員、学生または組織の一員ではないユーザーを指します。 ゲストは組織内での学校アカウントまたは職場アカウントを持ちません。 たとえば、ゲストにはパートナー、製造元、供給元、コンサルタントなどが含まれます。 すべてのユーザーは、マイクロソフトのチームでは、ゲストとして追加できます。 これは、(Azure Active Directory アカウント) を使用して企業や消費者の電子メール アカウント (Outlook.com、Gmail.com またはその他のユーザー) を持つすべてのユーザーがチーム チャット、会議、およびファイルへのフル アクセスを持つチームにゲストとして参加できることを意味します。

来園者はチームでは、同じコンプライアンスと監査の保護として、Office 365 の残りの部分についてし、Azure AD 内で安全に管理することができます。

> [!NOTE]
> スタンドアロン Office 365 サブスクリプション プランを使用して組織内のユーザーのみ、Exchange オンライン計画 2 など招待できない組織には、来園者としてチームがこれらのユーザーに同じ組織に属していると見なされるためです。 チームを使用するこれらのユーザーに割り当てる必要があります、Office 365 のビジネス プレミアム、Office 365 の企業、または Office 365 の教育のサブスクリプション。  
      
Teams では、企業データを完全に制御して保持しながら、チーム、ドキュメント、リソース、チャット、アプリケーションへの外部アクセスをパートナーに提供できます。 来園者は Azure Active Directory 内で安全に管理できるし、同じコンプライアンスと監査の保護として、Office 365 の残りの部分は来園者はチームで対応します。 

## <a name="how-does-guest-access-compare-to-federation-external-access"></a>ゲスト アクセスはフェデレーション (外部アクセス) にどのような比較をするでしょうか。

ゲスト アクセスは、(フェデレーションとも呼ばれます) の外部アクセスから次のように異なります。

-   ゲスト アクセス権を持つは、ゲスト ユーザーは、特定チームのユーザーは、招待されたし、チャネルおよびファイルなどのチームに固有のリソースにアクセスできるチームへのアクセスを持ちます。 ゲスト ユーザーのチャットし、チームのメンバーを呼び出すことができますも。

-   フェデレーションまたは外部からのアクセスでは、外部ユーザーですることが 1 対 1 のチャットと通話別の組織内のユーザーとチームまたは Skype のいずれかを使用してビジネスの。 フェデレーション ユーザーは、チーム リソースにアクセスできません。 ゲスト アクセスと比べると、外部からのアクセスは、明示的な招待状のない組織の間の通信 (ポリシーで許可されている) 場合が、チャットにのみに限定されます。

## <a name="teams-and-office-365-groups"></a>チームと Office 365 のグループ

チームでは、Office 365 のグループが適用され、Office 365 のグループの共有アセットにアクセスするための新しい方法が用意されています。 Teams は、グループ/チーム メンバー間の常設チャットに最適なソリューションです。 Office 365 グループは、SharePoint サイトや Power BI ダッシュボードなどの一連の共有チーム資産を利用するために、クロス アプリケーションのメンバーシップを提供し、チームが効果的かつ安全にコラボレーションできるようにするサービスです。

## <a name="more-information"></a>詳細情報

 
  
    
  [Microsoft Teams のサポート リソース](support-resources.md)  
 
  

    

  
|  |  |
|---------|---------|
| Deep Dive into Guest Access (ゲスト アクセスの詳細)   | <iframe width="350" height="200" src="https://www.youtube.com/embed/D8DW2Urv5y8" frameborder="0" allowfullscreen></iframe>   |
| Microsoft Teams でのゲスト アクセスの有効化   | <iframe width="350" height="200" src="https://www.youtube.com/embed/g21Hcqdl5tI" frameborder="0" allowfullscreen></iframe>   |
 | Microsoft Teams でのゲストの追加   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
    

