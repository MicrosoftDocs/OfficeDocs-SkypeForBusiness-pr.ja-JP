---
title: オンボード チェックリスト - Microsoft 365 または Office 365 サービスを有効にする
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Microsoft 365 または Teams のOffice 365を構成する場合は、このチェックリストのコアタスク、To Do タスク、アクティビティに従ってください。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.collection:
- M365-collaboration
ms.openlocfilehash: b4464b2c2500657fcdcd86e9e1b1d800b7d62df5
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269872"
---
# <a name="enable-microsoft-365-or-office-365"></a>Microsoft 365 または Office 365を有効にする
 
| いいえ | アクティビティまたはタスク| 説明| 完了状態 | その他の情報|
|----|-----------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | Microsoft 365 またはOffice 365組織を作成する| 組織が Teams の利点を享受できるようにするには、Microsoft 365 またはOffice 365組織を設定する必要があります。 Microsoft 365 またはOffice 365組織がない場合は、「**追加情報**」列のガイダンスを参照してください。 | | [ビジネス向けの Microsoft 365 またはOffice 365を設定する](https://support.office.com/article/Set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa) <br/><br/>[追加のサポートが必要な場合は、Microsoft 365 またはOffice 365 チームのMicrosoft FastTrackを利用できます。](https://fasttrack.microsoft.com/office) |
| 2  | Microsoft 365 または Office 365 ライセンスを購入する | Teams の構想フェーズで行った作業の成果に基づいて、調達グループと協力して、組織が必要なライセンス SKU またはアドオン サービスを購入し、テナントに割り当てる準備が整っていることを確認します。 | | [Microsoft Teams サービスの説明](/office365/servicedescriptions/teams-service-description) <br/><br/>[Microsoft 365 または Office 365 for Business サブスクリプションのライセンスを購入する](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1) |
| 3  | Microsoft 365 または Office 365 ライセンスを組織に割り当てる | 通常、お客様またはライセンス管理者は、Microsoft ライセンスから Microsoft 365 またはOffice 365組織にライセンスを追加するためのリンクを受け取ります。 <br/><br/>ライセンスの購入に使用したチャネルによっては、[ **追加情報** ] 列に記載されているガイドのいずれかにアクセスすることが必要になる場合があります。 | | [プロダクト キーを使用するために支払われたサブスクリプションにライセンスを追加する](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53) <br/><br/>[ボリューム ライセンス サービス センターを通じて購入したサブスクリプションにライセンスを追加する](https://support.office.com/article/Add-licenses-to-a-subscription-purchased-through-the-Volume-Licensing-Service-Center-82ba88fa-ebdf-4d44-a7b3-cea82b25d71a) |
| 4  | 省略可能: 通信クレジットを有効にする | コミュニケーション クレジットは、組織の会議ブリッジの電話番号に無料でアクセスしたり、会議の開催者に国際会議参加者にダイヤルアウトする機能を提供したりするために使用するオプションの機能です。 <br/><br/>標準のユーザーごとの電話会議ライセンスに加えて、ボリュームおよびライセンス組織は、電話会議機能を有効にする分単位の料金プランを選択できます。 <br/><br/>組織に通信クレジットが必要かどうかを決定し、その場合は、テナントに Communications Credits アドオン ライセンスを追加して有効にします。 | | [コミュニケーション クレジットについて](what-are-communications-credits.md) <br/><br/>[組織用にコミュニケーション クレジットをセットアップする](set-up-communications-credits-for-your-organization.md) <br/><br/>[分数ごと従量課金制電話会議](audio-conferencing-pay-per-minute.md) |
| 5  | ライセンスが Microsoft 365 またはOffice 365組織で使用できることを確認する | Microsoft 365 管理センターに移動し、Microsoft 365 またはOffice 365組織で予想されるライセンス SKU と数量が表示されていることを確認します。 <br/><br/>このプロセスの詳細 **については、「追加情報」** の参照を使用してください。 | | [ビジネス サブスクリプションの Microsoft 365 またはOffice 365は何がありますか?](https://support.office.com/article/What-Office-365-for-business-subscription-do-I-have-092252f8-08df-4cdb-a8d2-b8653caa29a1) |
| 6  | ID 用に環境を構成します。 | ユーザーは、Microsoft 365 で作成することも、直接 (オンライン デプロイ モデルで) Office 365することも、オンプレミスの Active Directoryから Microsoft 365 またはOffice 365組織に同期することもできます。 <br/><br/>クラウド ID、同期された ID、またはフェデレーション ID を使用するかどうかを決定します。 適切な ID の種類を決定することは、このチェックリストの範囲外です。ただし、[ **追加情報]** 列には、これらのオプションに関する情報へのリンクがあります。 <br/><br/>**メモ：** 同期 ID またはフェデレーション ID を使用している場合は、オンプレミスのユーザー プリンシパル名 (UPN) が Microsoft 365 または Office 365 UPN と一致し、Azure AD Connect との同期に必要なすべての属性が構成されていることを確認します。 Teams に必要な属性については、Skype for Business Online の属性一覧を使用します。 | | [Microsoft 365 または Office 365 ID と Azure Active Directory について](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9) <br/><br/>[Microsoft 365 またはOffice 365へのディレクトリ同期を使用してユーザーをプロビジョニングする準備をする](https://support.office.com/article/Prepare-to-provision-users-through-directory-synchronization-to-Office-365-01920974-9e6f-4331-a370-13aea4e82b3e) <br/><br/>[Azure AD Connect 同期: Azure Active Directory に同期された属性](/azure/active-directory/connect/active-directory-aadconnectsync-attributes-synchronized) |
| 7  | テナント管理者を確認する | セキュリティ チームと協力して、Microsoft 365 または Office 365管理モデルを開発します。 <br/><br/>すべてのテナント管理者とサービス管理者を必ず特定し、文書化してください。 | | [Microsoft 365 またはOffice 365管理者ロールについて](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) |
| 8  | テナントの管理ロールを実装する | 管理モデルが組織のニーズを満たしていることを検証し、Microsoft 365 またはOffice 365管理者ロールを管理者に割り当てます。 | | [Microsoft 365 またはビジネス向けのOffice 365で管理者ロールを割り当てる](https://support.office.com/article/Assign-admin-roles-in-Office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) |
| 9  | 通話品質ダッシュボード (CQD) にサインインして、建物情報をアップロードします。 | すべての Teams 展開では、CQD を利用して、Teams を使用するすべての呼び出しの品質と信頼性に関する分析情報を得る必要があります。 <br><br>このツールを最大限に活用するには、[ **追加情報]** 列に記載されている CQD ガイダンスを使用します。 | | [サービス管理と品質の計画](./prepare-network.md) <br/><br/>[品質エクスペリエンスのレビュー ガイド](./quality-of-experience-review-guide.md) <br/><br/>[Quality Experience Review テンプレート](https://aka.ms/qertemplates) <br/><br/>[Microsoft Teams と Skype for Business Online の通話品質ダッシュボードのオンと使用](https://support.office.com/article/Turning-on-and-using-Call-Quality-Dashboard-for-Microsoft-Teams-and-Skype-for-Business-Online-553fa13c-92d2-4d5c-a3d5-41a073cb047c)<br><br>[建物情報をアップロードする](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) |
| 10  | 建物情報が処理され、通話品質ダッシュボード (CQD) がテナントに対して操作可能であることを検証します。 | | | [通話品質ダッシュボード](https://cqd.teams.microsoft.com) |