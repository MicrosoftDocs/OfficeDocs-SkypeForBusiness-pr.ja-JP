---
title: Teams Contoso のケース スタディ
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365solution-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams企業向け音声ケース スタディ
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19200ec5ab1556b0f2b4fda2f389e60bc236015b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097493"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a>Contoso のケース スタディ: Teams移行の概要

この記事では、架空の多国籍企業 Contoso が組織に対して音声ソリューションを実装Teamsケース スタディを紹介します。

Contoso は Microsoft 365 Enterprise を展開し、ネットワーク、ID、Windows 10 Enterprise、Office 365 ProPlus、モバイル デバイス管理、情報保護、セキュリティ、Skype for Business から Teams、電話システム、電話会議へのアップグレードに関する主要な設計上の決定と実装の詳細に対処しました。  

この記事では、Contoso がオンプレミスのユーザーを統合コミュニケーション、コラボレーション、音声Teamsに移行した方法について説明します。 Contoso が Microsoft のクラウド サービスを使用してデジタル変革を加速した背景情報については、Contoso のケース スタディの概要から始まるすべての主要な記事 [を参照してください](/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide)。

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

主要な記事では、次の情報を確認できます。  

- Contoso の IT インフラストラクチャのニーズ
- ネットワーク
- Identity
- Windows 10 Enterprise
- Office 365 Pro Plus
- モバイル デバイスの管理
- 情報保護
- セキュリティのMicrosoft 365 Enterprise概要
- トップシークレット プロジェクトのチーム
- SharePoint機密性の高いデジタル資産のオンライン サイト

アップグレードの計画については、アップグレードの概要に関するMicrosoft Teams[があります](upgrade-start-here.md)。

## <a name="contoso-business-goals-for-teams"></a>Contoso のビジネス目標Teams

Contoso は、統合された通信、コラボレーション、音声Teamsにオンプレミス ユーザーを移行するために、次のビジネス目標を決定しました。

- Teams有効化 

  Contoso の統合されたコミュニケーションおよびコラボレーション チームは、Teamsおよび外部のコラボレーションを管理し、有効にする適切なポリシーを使用して統合を有効にしました。 

- Skype for Business から Teams へのアップグレード 

  Skype for Business Contoso 内に広く展開されました。 レガシ システムから移行する必要がある場合、Contoso はユーザーを新しいシステムにSkype for BusinessアップグレードTeams。 詳細については、「Contoso のケース[スタディ: アップグレード プランTeams参照してください](voice-case-study-migration-plan.md)。

- 電話システム  

  Skype for Businessは、Contoso 内に広く展開されました。 仲介サーバーの次ホップであるレガシ システムから移行する必要がある場合、Contoso はエンタープライズ音声ユーザーをSkype for Businessに移行電話システム。 Contoso サイトでは、Microsoft 通話プラン、電話システムルーティング、または両方の組み合わせを使用しました。 詳細については、「Contoso のケース[スタディ: 電話システム」 を参照してください](voice-case-study-phone-system.md)。

- 場所に基づくルーティング 

  テレフォニー規制対象国のオフィスの場所では、Contoso は、Location-Based の展開で Skype for Business に存在する 電話システム ルーティングを再作成する必要がありました。 詳細については、「Contoso のケース [スタディ: ルーティングのLocation-Based参照してください](voice-case-study-location-based-routing.md)。

- 緊急通話 

  直接ルーティングが実装された場所で、Contoso は承認されたサード パーティとの緊急通話を設定しました。 詳細については、「Contoso のケース [スタディ: 緊急通話」を参照してください](voice-case-study-emergency-calling.md)。

- 電話会議 

  Contoso は、SIP トランクでホストされた電話会議サービス番号を PSTN プロバイダーに設定します。 詳細については、「Contoso のケース [スタディ: 電話会議」を参照してください](voice-case-study-audio-conferencing.md)。 

- ローカル メディアの最適化 

  Contoso は、リモート サイトで利用された Microsoft 電話 システムへの 1 つの直接ルート トランクを持つ場所で、ローカル メディアの最適化を利用しました。 詳細については、「ローカル メディアの最適化 [を計画する」](direct-routing-media-optimization.md) および「ローカル メディアの最適化 [を構成する」を参照してください](direct-routing-media-optimization-configure.md)。

- 自動応答と通話キュー

  Covid-19 の結果、Contoso はスタッフがリモートで作業している間に受付のサポートを提供したいと考えたのです。 Contoso は、自動応答と通話キューを使用して、受付の電話番号への着信通話を管理しました。 詳細については、「Contoso のケース [スタディ: 自動応答と通話キュー」を参照してください](voice-case-study-call-queues.md)。