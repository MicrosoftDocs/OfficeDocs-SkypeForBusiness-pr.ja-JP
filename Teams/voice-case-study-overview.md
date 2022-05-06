---
title: Teams音声 Contoso のケース スタディの概要
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
description: 'Teams多国籍企業向けの音声ケース スタディ: 音声移行の概要'
appliesto:
- Microsoft Teams
ms.openlocfilehash: fa9c4e3e8468723d4e0fce7f2fa5a61646213260fe16a3c137b6c8fe7e01a635
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54319630"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a>Contoso のケース スタディ: Teams音声移行の概要

この記事では、架空の多国籍企業 Contoso が組織に対してTeams音声ソリューションを実装した方法に関するケース スタディについて説明します。

Contoso はMicrosoft 365 Enterpriseを展開し、ネットワーク、ID、Windows 10 Enterprise、Office 365 ProPlus、モバイル デバイス管理、情報保護、セキュリティ、アップグレードの主な設計上の決定と実装の詳細に対処しました。Teams、電話システム、電話会議にSkype for Businessします。  

この記事では、Contoso がオンプレミス ユーザーを統合コミュニケーション、コラボレーション、音声のためにTeamsに移行した方法について説明します。 Microsoft のクラウド サービスを使用して Contoso がどのようにデジタル変革を加速したかの背景情報については、 [Contoso のケース スタディの概要](/microsoft-365/enterprise/contoso-case-study)から始まるすべてのコア記事を参照してください。

[https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study](/microsoft-365/enterprise/contoso-case-study) 

コア記事では、次の情報を確認できます。  

- Contoso の IT インフラストラクチャのニーズ
- ネットワーク
- Identity
- Windows 10 Enterprise
- Office 365 Pro Plus
- モバイル デバイス管理
- 情報保護
- Microsoft 365 Enterpriseセキュリティの概要
- トップシークレット プロジェクトのチーム
- 機密性の高いデジタル資産のオンライン サイトをSharePointする

アップグレードの計画の詳細については、Microsoft Teamsアップグレードの概要から始める[必要があります](upgrade-start-here.md)。

## <a name="contoso-business-goals-for-teams"></a>Teamsの Contoso ビジネス目標

Contoso は、オンプレミス ユーザーを統合コミュニケーション、コラボレーション、音声のTeamsに移行するために、次のビジネス目標を決定しました。

- Teams有効化 

  Contoso の統合コミュニケーションとコラボレーション チームは、セキュリティで保護された内部および外部コラボレーションを管理し、有効にする適切なポリシーを使用してTeamsを有効にしました。 

- Skype for Business から Teams へのアップグレード 

  Skype for Businessは Contoso 内に広く展開されました。 従来のシステムから移行する必要がある中で、Contoso はSkype for Business ユーザーをTeamsにアップグレードすることにしました。 詳細については、「[Contoso のケース スタディ: Teamsアップグレード プラン](voice-case-study-migration-plan.md)」を参照してください。

- 電話システム  

  エンタープライズ音声を使用したSkype for Businessは、Contoso 内に広く展開されました。 Contoso は、仲介サーバーの次ホップであったレガシ システムから移行する必要がありましたが、Skype for Businessエンタープライズ音声ユーザーを電話システムに移行しました。 Contoso サイトでは、Microsoft 通話プラン、電話システムダイレクト ルーティング、またはその両方の組み合わせを使用しました。 詳細については、「[Contoso のケース スタディ: 電話システム](voice-case-study-phone-system.md)」を参照してください。

- 場所に基づくルーティング 

  Contoso は、テレフォニー規制の国のオフィスの場所で、電話システムの展開でSkype for Businessに存在していたLocation-Basedルーティングを再作成する必要がありました。 詳細については、「 [Contoso のケース スタディ: Location-Based ルーティング](voice-case-study-location-based-routing.md)」を参照してください。

- 緊急通話 

  ダイレクト ルーティングが実装された場所で、Contoso は承認されたサード パーティとの緊急通話を設定しました。 詳細については、「 [Contoso のケース スタディ: 緊急通話」を](voice-case-study-emergency-calling.md)参照してください。

- 電話会議 

  Contoso は、SIP トランクで PSTN プロバイダーにホストされていた電話会議サービス番号を設定しました。 詳細については、「 [Contoso のケース スタディ: 電話会議」を](voice-case-study-audio-conferencing.md)参照してください。 

- ローカル メディアの最適化 

  Contoso は、リモート サイトによって利用された Microsoft 電話 システムへの 1 つのダイレクト ルート トランクがある場所で、ローカル メディアの最適化を利用しました。 詳細については、「[ローカル メディアの最適化の計画とローカル メディアの最適化](direct-routing-media-optimization.md)[の構成」を参照](direct-routing-media-optimization-configure.md)してください。

- 自動応答と通話キュー

  Covid-19 の結果、Contoso はスタッフがリモートで作業している間、受付のサポートを提供したいと考えました。 Contoso は、自動応答と通話キューを使用して、受付担当者の電話番号への着信を管理しました。 詳細については、「 [Contoso のケース スタディ: 自動応答と通話キュー」を](voice-case-study-call-queues.md)参照してください。
