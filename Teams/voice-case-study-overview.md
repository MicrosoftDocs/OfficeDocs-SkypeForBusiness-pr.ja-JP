---
title: Teams の音声 Contoso のケース スタディ
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
description: 多国籍企業向け Teams 音声ケース スタディ
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19200ec5ab1556b0f2b4fda2f389e60bc236015b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097493"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a>Contoso のケース スタディ: Teams 音声移行の概要

この記事では、架空の多国籍企業 Contoso が組織に Teams 音声ソリューションを実装した方法について、ケース スタディについて説明します。

Contoso は Microsoft 365 Enterprise を展開し、ネットワーク、ID、Windows 10 Enterprise、Office 365 ProPlus、モバイル デバイス管理、情報保護、セキュリティ、Skype for Business から Teams、電話システム、電話会議にアップグレードする主な設計決定と実装の詳細に対応しました。  

この記事では、Contoso が統合コミュニケーション、コラボレーション、音声のためにオンプレミス ユーザーを Teams に移行した方法について説明します。 Microsoft のクラウド サービスを使用して Contoso がデジタル変換を高速化した方法に関する背景情報については、Contoso のケース スタディの概要から始まる主要なすべての記事 [を参照してください](/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide)。

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

主要な記事では、次の情報を参照できます。  

- Contoso の IT インフラストラクチャのニーズ
- ネットワーク
- Identity
- Windows 10 Enterprise
- Office 365 Pro Plus
- モバイル デバイス管理
- 情報保護
- Microsoft 365 Enterprise セキュリティの概要
- チームで最高のプロジェクトを作成する
- 機密性の高いデジタル資産の SharePoint Online サイト

アップグレードの計画については、Microsoft Teams のアップグレードの概要 [から始める必要があります](upgrade-start-here.md)。

## <a name="contoso-business-goals-for-teams"></a>Teams の Contoso ビジネスの目標

統合されたコミュニケーション、コラボレーション、音声のためにオンプレミス ユーザーを Teams に移行するために、Contoso は次のビジネス目標を決定しました。

- Teams の有効化 

  Contoso の統合コミュニケーションとコラボレーション チームは、適切なポリシーを使用して Teams を有効にし、内部と外部の安全なコラボレーションを制御し、有効にしました。 

- Skype for Business から Teams へのアップグレード 

  Skype for Business は Contoso 内に広く展開されました。 従来のシステムから移行する必要がある場合、Contoso は Skype for Business ユーザーを Teams にアップグレードすることを決定しました。 詳細については、「Contoso のケース スタディ: Teams アップグレード [プラン」を参照してください](voice-case-study-migration-plan.md)。

- 電話システム  

  エンタープライズ ボイス付き Skype for Business は、Contoso 内に広く展開されました。 仲介サーバーの次のホップである従来のシステムから移行する必要がある場合、Contoso は Skype for Business エンタープライズ 音声ユーザーを電話システムに移行しました。 Contoso サイトでは、Microsoft 通話プラン、電話システムダイレクト ルーティング、または両方の組み合わせを使用しました。 詳細については、「Contoso のケース [スタディ: 電話システム」を参照してください](voice-case-study-phone-system.md)。

- 場所に基づくルーティング 

  テレフォニーが規制された国のオフィスの場所では、Contoso は電話システムの展開で Skype for Business に存在する Location-Based ルーティングを再作成する必要がありました。 詳細については、「Contoso のケース [スタディ: Location-Based ルーティング」を参照してください](voice-case-study-location-based-routing.md)。

- 緊急通話 

  直接ルーティングが実装された場合、Contoso は承認された第三者との緊急通話を設定します。 詳細については、「Contoso のケース [スタディ: 緊急通話」を参照してください](voice-case-study-emergency-calling.md)。

- 電話会議 

  Contoso は、PSTN プロバイダーに SIP トランクでホストされている電話会議サービス番号を設定します。 詳細については、「Contoso のケース [スタディ: 電話会議」を参照してください](voice-case-study-audio-conferencing.md)。 

- ローカル メディアの最適化 

  Contoso は、リモート サイトで利用された Microsoft Phone System への直接ルート トランクが 1 つある場所で、ローカル メディア最適化を利用しました。 詳細については、「ローカル メディア最適化 [の計画」](direct-routing-media-optimization.md) および「ローカル メディアの最適化 [を構成する」を参照してください](direct-routing-media-optimization-configure.md)。

- 自動応答と通話キュー

  Covid-19 の結果として、Contoso はスタッフがリモートで作業している間、受付のサポートを提供する必要があります。 Contoso は、受付係の電話番号への着信通話を管理するために、自動応答と通話キューを使用しました。 詳細については、「Contoso のケース [スタディ: 自動応答と通話キュー」を参照してください](voice-case-study-call-queues.md)。