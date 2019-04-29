---
title: Microsoft Teams で Office 365 サービスを有効にするための使用開始チェックリスト
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Teams 用の Office 365 を構成するときに、このチェックリスト内の中核的な To Do タスクおよびアクティビティを実行します。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 62f5b3180a0153aa0600d4d80b90fe6c681af43e
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400649"
---
# <a name="enable-office-365"></a>Office 365 を有効にする
 
| いいえ | アクティビティまたはタスク| 説明| 完了状態 | 追加情報|
|----|-----------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| $1  | Office 365 テナントの作成| 組織が Teams のメリットを活用できるようになるには、Office 365 テナントをセットアップする必要があります。 Office 365 テナントがない場合は、**追加情報**列のガイダンスをご覧ください。 | | [法人向け Office 365 をセットアップする](https://support.office.com/article/Set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa) <br/><br/>[追加のサポートが必要な場合は、Microsoft FastTrack for Office 365 team を利用することができます](https://fasttrack.microsoft.com/office) |
| ●2  | Office 365 のライセンスを購入する | Teams の構想フェーズ中に行った作業の結果に基づいて、自分たちの調達グループと協力して、組織が必要なライセンス SKU またはアドオン サービスを購入済みで、それらがテナントに割り当てられる準備ができていることを確認します。 | | [Microsoft Teams 用の Office 365 ライセンス](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing) <br/><br/>[一般法人向け Office 365 サブスクリプションのライセンスを購入する](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1) |
| 3%  | テナントに Office 365 ライセンスを割り当てる | 通常、お客様自身またはお客様のライセンス管理者が、Office 365 テナントにライセンスを追加するためのリンクを Microsoft ライセンスから受け取ります。 <br/><br/>ライセンスを購入するために使用したチャネルによっては、**追加情報**列に表記されているガイドの 1 つにアクセスする必要がある場合があります。 | | [プロダクト キーを使用するための有料のサブスクリプションにライセンスを追加する](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53) <br/><br/>[ボリューム ライセンス サービス センターを介して購入したサブスクリプションにライセンスを追加する](https://support.office.com/article/Add-licenses-to-a-subscription-purchased-through-the-Volume-Licensing-Service-Center-82ba88fa-ebdf-4d44-a7b3-cea82b25d71a) |
| √(4)  | オプション: コミュニケーション クレジットを有効にする | コミュニケーション クレジットは、オプションの機能として、所属する組織の会議ブリッジの電話番号に対する無料アクセスを提供したり、電話会議の開催者に対して国際会議の参加者にダイヤル アウトする機能を提供したりするために使用します。 <br/><br/>標準の電話会議のユーザーごとのライセンスに加えて、ボリューム ライセンスを利用している組織は、分数ごとの従量課金制を選んで電話会議機能を有効にすることもできます。 <br/><br/>所属する組織でコミュニケーション クレジットが必要かどうかを判断します。必要である場合は、テナントにコミュニケーション クレジットのアドオン ライセンスを追加して有効にします。 | | [コミュニケーション クレジットについて](what-are-communications-credits.md) <br/><br/>[組織用にコミュニケーション クレジットをセットアップする](set-up-communications-credits-for-your-organization.md) <br/><br/>[分数ごと従量課金制電話会議](audio-conferencing-pay-per-minute.md) |
| 5 人の参加者  | Office 365 テナントに対してライセンスが利用可能であることを確認する | Office 365 管理ポータルに移動して、お使いの Office 365 テナントで必要なライセンス SKU と数量が表示されていることを確認します。 <br/><br/>このプロセスの手順を確認するには、**追加情報**の参照先を利用できます。 | | [現在利用している一般法人向け Office 365 サブスクリプションはどれでしょうか?](https://support.office.com/article/What-Office-365-for-business-subscription-do-I-have-092252f8-08df-4cdb-a8d2-b8653caa29a1) |
| 6 Mb  | ID のために環境を構成する | ユーザーは、(オンライン展開モデルの) Office 365 で直接作成されたり、オンプレミスの Active Directory から Office 365 テナントに同期されることができます。 <br/><br/>クラウド ID、同期された ID、フェデレーション ID のどれを使用するべきかを判断します。 最適な ID タイプがこのチェックリストの範囲外であると判断した場合でも、**追加情報**列に、これらのオプションに関する情報へのリンクがあります。 <br/><br/>**注:** 同期された ID またはフェデレーション ID を使用している場合は、オンプレミスのユーザー プリンシパル名 (UPN) が Office 365 UPN と一致することと、すべての必要な属性が Azure AD Connect と同期するために構成されていることを確認してください。 Teams で必要となる属性については、Skype for Business Online の属性リストで確認してください。 | | [Office 365 ID と Azure Active Directory について](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9) <br/><br/>[Office 365 へのディレクトリ同期を介したユーザーのプロビジョニングの準備をする](https://support.office.com/article/Prepare-to-provision-users-through-directory-synchronization-to-Office-365-01920974-9e6f-4331-a370-13aea4e82b3e) <br/><br/>[Azure AD Connect の同期: Azure Active Directory に同期される属性](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-attributes-synchronized) |
| 例 7  | テナント管理者を確認する | セキュリティ チームと協力して、Office 365 管理モデルを開発します。 <br/><br/>必ず、すべてのテナントとサービスの管理者を特定して記録します。 | | [Office 365 管理者ロールについて](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) |
| Windows 8  | お使いのテナント向けに管理者のロールを実装する | お使いの管理モデルが組織のニーズを満たすものであるかを検証して、管理者に Office 365 管理者ロールを割り当てます。 | | [一般法人向け Office 365 に管理者ロールを割り当てる](https://support.office.com/article/Assign-admin-roles-in-Office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) |
| 手順 9  | 通話品質ダッシュボード (CQD) にサインインして建物の情報をアップロードします。 | 各 Teams の展開では、Teams を使用するすべての通話の品質と信頼性についての洞察を得るために、CQD を利用する必要があります。 <br><br>このツールのメリットを最大限活用するには、**追加情報**列に記載されている CQD ガイダンスをご覧ください。 | | [サービス管理と品質の計画](https://docs.microsoft.com/MicrosoftTeams/envision-planning-for-service-management-and-quality-complete-guide) <br/><br/>[品質エクスペリエンスのレビュー ガイド](https://aka.ms/qerguide) <br/><br/>[品質エクスペリエンスのレビュー テンプレート](https://aka.ms/qertemplates) <br/><br/>[Microsoft Teams および Skype for Business Online で通話品質ダッシュボードをオンにして使用する](https://support.office.com/article/Turning-on-and-using-Call-Quality-Dashboard-for-Microsoft-Teams-and-Skype-for-Business-Online-553fa13c-92d2-4d5c-a3d5-41a073cb047c)<br><br>[建物の情報のアップロード](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard?#upload-building-information) |
| 10%  | 建物の情報が処理されていることと、通話品質ダッシュボード (CQD) がテナントで操作可能であることを確認します。 | | | [通話品質ダッシュボード](https://cqd.lync.com) |