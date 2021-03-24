---
title: オンボーディング チェックリスト - Microsoft 365 または Office 365 サービスを有効にする
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Teams 用の Microsoft 365 または Office 365 を構成する場合は、このチェックリストの主要な To Do タスクとアクティビティに従います。
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
# <a name="enable-microsoft-365-or-office-365"></a>Microsoft 365 または Office 365 を有効にする
 
| いいえ | アクティビティまたはタスク| 説明| 完了状態 | その他の情報|
|----|-----------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | Microsoft 365 または Office 365 組織を作成する| 組織が Teams の利点を利用するには、Microsoft 365 または Office 365 組織をセットアップする必要があります。 Microsoft 365 または Office 365 組織を持っている場合は、「追加情報」列のガイダンス **を参照** してください。 | | [一Office Microsoft 365 または Office 365 をセットアップする](https://support.office.com/article/Set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa) <br/><br/>[追加のサポートが必要な場合は、Microsoft FastTrack for Microsoft 365 または Office 365 チームが](https://fasttrack.microsoft.com/office) |
| 2  | Microsoft 365 または Office 365 ライセンスを購入する | Teams Envision フェーズで行った作業の結果に基づいて、調達グループと一緒に作業し、組織が必要なライセンス SKU またはアドオン サービスを購入し、テナントに割り当てる準備が整ったことを確認します。 | | [Microsoft Teams サービスの説明](/office365/servicedescriptions/teams-service-description) <br/><br/>[Microsoft 365 または Office 365 for Business サブスクリプションのライセンスを購入する](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1) |
| 3  | Microsoft 365 または Office 365 ライセンスを整理に割り当てる | 通常、お客様またはライセンス管理者は、Microsoft 365 または Office 365 組織にライセンスを追加するリンクを Microsoft ライセンスから受け取る必要があります。 <br/><br/>ライセンスの購入に使用したチャネルによっては、[追加情報] 列に記載されているガイドにアクセスする **必要がある場合** があります。 | | [プロダクト キーを使用して支払われたサブスクリプションにライセンスを追加する](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53) <br/><br/>[ボリューム ライセンス サービス センターを通じて購入したサブスクリプションにライセンスを追加する](https://support.office.com/article/Add-licenses-to-a-subscription-purchased-through-the-Volume-Licensing-Service-Center-82ba88fa-ebdf-4d44-a7b3-cea82b25d71a) |
| 4  | オプション: 通信クレジットを有効にする | コミュニケーション クレジットは、組織の電話会議ブリッジの電話番号に無料でアクセスしたり、会議開催者に国際会議の参加者にダイヤルアウトする機能を提供したりするために使用するオプションの機能です。 <br/><br/>ボリューム/ライセンス組織は、標準的な電話会議のユーザーごとのライセンスに加えて、分単位支払いサービスを選択して電話会議機能を有効にできます。 <br/><br/>組織に通信クレジットが必要かどうかを決定し、必要な場合は、テナントに通信クレジット アドオン ライセンスを追加して有効にします。 | | [コミュニケーション クレジットについて](what-are-communications-credits.md) <br/><br/>[組織用にコミュニケーション クレジットをセットアップする](set-up-communications-credits-for-your-organization.md) <br/><br/>[分数ごと従量課金制電話会議](audio-conferencing-pay-per-minute.md) |
| 5  | Microsoft 365 または Office 365 組織でライセンスを利用Office確認する | Microsoft 365 管理センターに移動し、Microsoft 365 または Office 365 組織で必要なライセンス SKU と数量が表示Officeします。 <br/><br/>このプロセスの手順 **については、「** 追加情報」の参照を使用してください。 | | [取得している一Office Microsoft 365 または 365 for Business サブスクリプション](https://support.office.com/article/What-Office-365-for-business-subscription-do-I-have-092252f8-08df-4cdb-a8d2-b8653caa29a1) |
| 6  | ID 用に環境を構成します。 | ユーザーは、Microsoft 365 または Office 365 で (オンライン展開モデルで) 直接作成するか、オンプレミスの Active Directory から Microsoft 365 または Office 365 組織に同期することができます。 <br/><br/>クラウド ID、同期 ID、またはフェデレーション ID を使用するかどうかを決定します。 適切な ID の種類の特定は、このチェックリストの対象から外されています。ただし、[追加情報] 列には、これらのオプションに関する情報 **へのリンクが表示** されます。 <br/><br/>**注:** 同期 ID またはフェデレーション ID を使用している場合は、オンプレミスのユーザー プリンシパル名 (UPN) が Microsoft 365 または Office 365 の UPN と一致し、Azure AD Connect と同期するために必要なすべての属性が構成されていることを確認します。 Teams に必要な属性については、Skype for Business Online の属性リストを使用します。 | | [Microsoft 365 または Office 365 ID と Azure Active Directory について](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9) <br/><br/>[Microsoft 365 または Office 365 へのディレクトリ同期を通じてユーザーをプロビジョニングする準備をする](https://support.office.com/article/Prepare-to-provision-users-through-directory-synchronization-to-Office-365-01920974-9e6f-4331-a370-13aea4e82b3e) <br/><br/>[Azure AD Connect 同期: Azure Active Directory に同期された属性](/azure/active-directory/connect/active-directory-aadconnectsync-attributes-synchronized) |
| 7  | テナント管理者の確認 | セキュリティ チームと一緒に Microsoft 365 または Office 365 管理モデルを開発します。 <br/><br/>テナントとサービスのすべての管理者を特定して文書化してください。 | | [Microsoft 365 または Office 365 管理者ロールについて](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) |
| 8  | テナントの管理ロールを実装する | 管理モデルが組織のニーズを満たしたと検証し、Microsoft 365 または Office 365 の管理者ロールを管理者に割り当てます。 | | [Microsoft 365 または一Office 365 で管理者ロールを割り当てる](https://support.office.com/article/Assign-admin-roles-in-Office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) |
| 9  | 通話品質ダッシュボード (CQD) にサインインして建物情報をアップロードします。 | すべての Teams の展開では、CQD を活用して、Teams を使用するすべての呼び出しの品質と信頼性に関する洞察を得る必要があります。 <br><br>このツールを最も利用するには、[追加情報]列に記載されている CQD ガイダンスを使用します。 | | [サービス管理と品質の計画](./prepare-network.md) <br/><br/>[品質エクスペリエンスのレビュー ガイド](./quality-of-experience-review-guide.md) <br/><br/>[品質エクスペリエンスのレビュー テンプレート](https://aka.ms/qertemplates) <br/><br/>[Microsoft Teams および Skype for Business Online の通話品質ダッシュボードをオンにして使用する](https://support.office.com/article/Turning-on-and-using-Call-Quality-Dashboard-for-Microsoft-Teams-and-Skype-for-Business-Online-553fa13c-92d2-4d5c-a3d5-41a073cb047c)<br><br>[建物情報をアップロードする](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) |
| 10  | 建物情報が処理され、通話品質ダッシュボード (CQD) がテナントで操作可能な場合に検証します。 | | | [通話品質ダッシュボード](https://cqd.teams.microsoft.com) |