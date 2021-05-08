---
title: オンボード チェックリスト - サービスのMicrosoft 365またはOffice 365する
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: このチェックリストのコアタスク、To Do タスク、アクティビティに従って、Microsoft 365またはOffice 365をTeams。
localization_priority: Normal
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 54358269658ec7fc531bc6e18c3b08eab817040d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098023"
---
# <a name="enable-microsoft-365-or-office-365"></a>設定またはMicrosoft 365を有効Office 365
 
| いいえ | アクティビティまたはタスク| 説明| 完了状態 | その他の情報|
|----|-----------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | 組織をMicrosoft 365またはOffice 365する| 組織が新しい組織の利点を利用するにはTeams組織または組織にMicrosoft 365するOffice 365があります。 組織の管理者または組織がMicrosoft 365場合Office 365、[追加情報] 列のガイダンス **を参照** してください。 | | [一Microsoft 365またはOffice 365を設定する](https://support.office.com/article/Set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa) <br/><br/>[追加のサポートが必要な場合は、Microsoft FastTrack for Microsoft 365 または Office 365 チームがサポートを受け取っています。](https://fasttrack.microsoft.com/office) |
| 2  | ライセンスMicrosoft 365購入またはOffice 365する | Teams Envision フェーズで行った作業の結果に基づいて、調達グループと作業して、組織が必要なライセンス SKU またはアドオン サービスを購入し、テナントに割り当てる準備ができていることを確認します。 | | [Microsoft Teamsの説明](/office365/servicedescriptions/teams-service-description) <br/><br/>[Microsoft 365 または Office 365 for Business サブスクリプションのライセンスを購入する](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1) |
| 3  | 組織Microsoft 365またはOffice 365ライセンスを割り当てる | 通常、お客様またはライセンス管理者は、Microsoft ライセンスからリンクを受け取り、ライセンスを組織または組織Microsoft 365追加Office 365します。 <br/><br/>ライセンスの購入に使用したチャネルによっては、[追加情報] 列に記載されているガイドのいずれかを参照 **する必要がある場合** があります。 | | [プロダクト キーを使用して支払われたサブスクリプションにライセンスを追加する](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53) <br/><br/>[ボリューム ライセンス サービス センターを通じて購入したサブスクリプションにライセンスを追加する](https://support.office.com/article/Add-licenses-to-a-subscription-purchased-through-the-Volume-Licensing-Service-Center-82ba88fa-ebdf-4d44-a7b3-cea82b25d71a) |
| 4  | 省略可能: 通信クレジットを有効にする | コミュニケーション クレジットは、組織の電話会議ブリッジの電話番号に無料でアクセスしたり、会議開催者に国際会議の参加者にダイヤルアウトする機能を提供したりするために使用するオプションの機能です。 <br/><br/>ボリュームおよびライセンス組織は、標準的な電話会議のユーザーごとのライセンスに加えて、分単位の支払いオファーを選択して電話会議機能を有効にできます。 <br/><br/>組織に通信クレジットが必要かどうかを決定し、必要な場合は、テナントにコミュニケーション クレジット アドオン ライセンスを追加して有効にします。 | | [コミュニケーション クレジットについて](what-are-communications-credits.md) <br/><br/>[組織用にコミュニケーション クレジットをセットアップする](set-up-communications-credits-for-your-organization.md) <br/><br/>[分数ごと従量課金制電話会議](audio-conferencing-pay-per-minute.md) |
| 5  | ライセンスが組織または組織で使用Microsoft 365確認Office 365します | Microsoft 365 管理センターに移動し、組織のライセンス SKU と数量が表示Microsoft 365確認Office 365します。 <br/><br/>「追加情報」の **参照を** 使用して、このプロセスについて説明します。 | | [一Microsoft 365サブスクリプションOffice 365持っているサブスクリプションまたはサブスクリプションは何ですか?](https://support.office.com/article/What-Office-365-for-business-subscription-do-I-have-092252f8-08df-4cdb-a8d2-b8653caa29a1) |
| 6  | ID 用に環境を構成します。 | ユーザーは、Microsoft 365 または Office 365 で直接 (オンライン デプロイ モデルで) 作成するか、オンプレミスの Active Directory から Microsoft 365 または Office 365 組織に同期できます。 <br/><br/>クラウド ID、同期 ID、またはフェデレーション ID を使用するかどうかを決定します。 適切な ID の種類の特定は、このチェックリストの範囲を外しています。ただし、[追加情報] 列には、これらのオプションに関する情報 **へのリンクがあります** 。 <br/><br/>**注:** 同期 ID またはフェデレーション ID を使用している場合は、オンプレミスのユーザー プリンシパル名 (UPN) が Microsoft 365 または Office 365 UPN と一致し、必要なすべての属性が Azure AD Connect と同期するように構成されていることを確認します。 [オンライン] に必要な属性Teams Online の属性一覧Skype for Businessします。 | | [ID とMicrosoft 365のOffice 365についてAzure Active Directory](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9) <br/><br/>[ディレクトリ同期を使用してユーザーをプロビジョニングする準備を行い、Microsoft 365またはOffice 365](https://support.office.com/article/Prepare-to-provision-users-through-directory-synchronization-to-Office-365-01920974-9e6f-4331-a370-13aea4e82b3e) <br/><br/>[Azure AD Connect同期: 同期された属性Azure Active Directory](/azure/active-directory/connect/active-directory-aadconnectsync-attributes-synchronized) |
| 7  | テナント管理者の確認 | セキュリティ チームと一緒に、管理モデルMicrosoft 365またはOffice 365開発します。 <br/><br/>すべてのテナント管理者とサービス管理者を特定して文書化してください。 | | [管理者Microsoft 365ロールOffice 365ロールについて](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) |
| 8  | テナントの管理ロールを実装する | 管理モデルが組織のニーズを満たMicrosoft 365管理者ロールOffice 365割り当てます。 | | [一Microsoft 365または一Office 365管理者ロールを割り当てる](https://support.office.com/article/Assign-admin-roles-in-Office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) |
| 9  | 通話品質ダッシュボード (CQD) にサインインし、建物情報をアップロードします。 | すべてのTeamsデプロイでは、CQD を活用して、CQD を使用するすべての呼び出しの品質と信頼性に関する分析情報をTeams。 <br><br>[追加情報] 列に記載されている CQD ガイダンスを使用して、このツールのメリットを最も高くします。  | | [サービス管理と品質の計画](./prepare-network.md) <br/><br/>[品質エクスペリエンスのレビュー ガイド](./quality-of-experience-review-guide.md) <br/><br/>[品質エクスペリエンス レビュー テンプレート](https://aka.ms/qertemplates) <br/><br/>[通話品質ダッシュボードをオンにし、Microsoft Teams Online Skype for Businessする](https://support.office.com/article/Turning-on-and-using-Call-Quality-Dashboard-for-Microsoft-Teams-and-Skype-for-Business-Online-553fa13c-92d2-4d5c-a3d5-41a073cb047c)<br><br>[アップロードの情報](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) |
| 10  | 建物の情報が処理され、テナントに対して通話品質ダッシュボード (CQD) が操作可能なと検証します。 | | | [通話品質ダッシュボード](https://cqd.teams.microsoft.com) |