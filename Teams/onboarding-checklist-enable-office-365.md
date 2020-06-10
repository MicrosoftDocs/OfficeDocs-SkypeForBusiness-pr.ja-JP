---
title: オンボードチェックリスト-Microsoft 365 または Office 365 サービスを有効にする
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: このチェックリストで、チーム用に Microsoft 365 または Office 365 を構成するときに、基本的な to do タスクとアクティビティに従います。
localization_priority: Normal
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2439a2fd23566c93fb60772112da098cff315760
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "44665169"
---
# <a name="enable-microsoft-365-or-office-365"></a>Microsoft 365 または Office 365 を有効にする
 
| X | アクティビティまたはタスク| 説明| 完了状態 | その他の情報|
|----|-----------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | Microsoft 365 または Office 365 組織を作成する| 組織で Teams のメリットを享受するには、Microsoft 365 または Office 365 組織をセットアップする必要があります。 Microsoft 365 または Office 365 組織を持っていない場合は、「**追加情報**」列のガイダンスを参照してください。 | | [Microsoft 365 または Office 365 for business をセットアップする](https://support.office.com/article/Set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa) <br/><br/>[追加のサポートが必要な場合は、microsoft FastTrack for Microsoft 365 または Office 365 チームのサポートを利用できます。](https://fasttrack.microsoft.com/office) |
| 2  | Microsoft 365 または Office 365 ライセンスを購入する | Teams Envision のフェーズで行った作業の結果に基づいて、調達グループと協力して、必要なライセンス Sku またはアドオンサービスが組織で購入されていることを確認し、テナントに割り当てる準備ができていることを確認します。 | | [Microsoft Teams サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description) <br/><br/>[Microsoft 365 または一般法人向け Office 365 サブスクリプションのライセンスを購入する](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1) |
| 3  | Microsoft 365 または Office 365 のライセンスをオーガナイザーに割り当てる | 通常、お客様またはライセンス管理者は、microsoft ライセンスのリンクを受け取って、Microsoft 365 または Office 365 組織にライセンスを追加します。 <br/><br/>ライセンスの購入に使用したチャネルによっては、[**追加情報**] 列に示されているガイドのいずれかにアクセスしなければならない場合があります。 | | [プロダクトキーを使って支払われたサブスクリプションにライセンスを追加する](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53) <br/><br/>[ボリュームライセンスサービスセンター経由で購入したサブスクリプションにライセンスを追加する](https://support.office.com/article/Add-licenses-to-a-subscription-purchased-through-the-Volume-Licensing-Service-Center-82ba88fa-ebdf-4d44-a7b3-cea82b25d71a) |
| 4  | オプション: 通信クレジットを有効にする | 通信クレジットは、組織の電話番号への無料アクセスを提供するために使用するオプションの機能です。または、会議開催者が国際会議の出席者にダイヤルアウトする機能を提供するために使用します。 <br/><br/>標準の電話会議に加えて、ユーザーごとのライセンス、ボリューム、ライセンス組織では、電話会議機能を有効にするために、1分あたりの料金プランを選ぶことができます。 <br/><br/>組織で通信クレジットが必要かどうかを決定します。その場合は、通信クレジットのアドオンライセンスをテナントに追加して有効にすることができます。 | | [コミュニケーション クレジットについて](what-are-communications-credits.md) <br/><br/>[組織用にコミュニケーション クレジットをセットアップする](set-up-communications-credits-for-your-organization.md) <br/><br/>[分数ごと従量課金制電話会議](audio-conferencing-pay-per-minute.md) |
| 5  | Microsoft 365 または Office 365 組織でライセンスが利用可能であることを確認する | Microsoft 365 管理センターに移動し、Microsoft 365 または Office 365 組織で想定されていたライセンスの Sku と数量が示されていることを確認します。 <br/><br/>このプロセスで説明する**追加情報**のリファレンスを使用します。 | | [使用している Microsoft 365 または Office 365 for business のサブスクリプション](https://support.office.com/article/What-Office-365-for-business-subscription-do-I-have-092252f8-08df-4cdb-a8d2-b8653caa29a1) |
| 6  | Id の環境を構成します。 | ユーザーは、Microsoft 365 または Office 365 で直接 (オンライン展開モデルの場合)、またはオンプレミスの Active Directory から Microsoft 365 または Office 365 組織に同期することができます。 <br/><br/>クラウド id、同期された id、またはフェデレーション id を使用する必要があるかどうかを決定します。 適切な id の種類の決定は、このチェックリストの範囲外です。ただし、これらのオプションの詳細については、[**追加情報**] 列を参照してください。 <br/><br/>**注:** 同期 id またはフェデレーション id を使用している場合は、オンプレミスのユーザープリンシパル名 (Upn) が Microsoft 365 または Office 365 Upn と一致しており、必要なすべての属性が Azure AD Connect との同期用に構成されていることを確認します。 Teams に必要な属性については、Skype for Business Online の属性リストを使用します。 | | [Microsoft 365 または Office 365 identity と Azure Active Directory について](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9) <br/><br/>[Microsoft 365 または Office 365 へのディレクトリ同期を通してユーザーをプロビジョニングするための準備](https://support.office.com/article/Prepare-to-provision-users-through-directory-synchronization-to-Office-365-01920974-9e6f-4331-a370-13aea4e82b3e) <br/><br/>[Azure AD Connect sync: Azure Active Directory に同期された属性](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-attributes-synchronized) |
| 7  | テナント管理者を確認する | セキュリティチームと協力して、Microsoft 365 または Office 365 の管理モデルを開発します。 <br/><br/>すべてのテナントとサービス管理者を特定して文書化してください。 | | [Microsoft 365 または Office 365 の管理者ロールについて](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) |
| 個  | テナントの管理者ロールを実装する | 管理モデルが組織のニーズを満たしていることを検証し、Microsoft 365 または Office 365 の管理者の役割を管理者に割り当てます。 | | [Microsoft 365 または一般法人向け Office 365 で管理者ロールを割り当てる](https://support.office.com/article/Assign-admin-roles-in-Office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) |
| ファイブ  | 通話品質ダッシュボード (CQD) にサインインして、建物情報をアップロードします。 | すべてのチーム展開では、CQD を活用して、Teams を使用するすべての通話の品質と信頼性を把握する必要があります。 <br><br>このツールを最大限に活用するには、[**追加情報**] 列に表示されている CQD のガイダンスを使用します。 | | [サービス管理と品質の計画](https://docs.microsoft.com/MicrosoftTeams/prepare-network) <br/><br/>[品質エクスペリエンスのレビュー ガイド](https://aka.ms/qerguide) <br/><br/>[品質エクスペリエンスレビューテンプレート](https://aka.ms/qertemplates) <br/><br/>[Microsoft Teams および Skype for Business Online で通話品質ダッシュボードをオンにして使用する](https://support.office.com/article/Turning-on-and-using-Call-Quality-Dashboard-for-Microsoft-Teams-and-Skype-for-Business-Online-553fa13c-92d2-4d5c-a3d5-41a073cb047c)<br><br>[建物情報のアップロード](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard?#upload-building-information) |
| 常用  | 建物情報が処理されていることを確認し、通話品質ダッシュボード (CQD) をテナントに対して操作することができます。 | | | [通話品質ダッシュボード](https://cqd.lync.com) |
