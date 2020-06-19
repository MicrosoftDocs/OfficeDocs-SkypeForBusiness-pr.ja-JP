---
title: チームボイスの Contoso のケーススタディ
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 多国籍企業向けの Teams の音声のケーススタディ
appliesto:
- Microsoft Teams
ms.openlocfilehash: 100889bacffdb9de722bd2e1e7295905876dab2e
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786085"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a>Contoso のケーススタディ: Teams の音声移行の概要

この記事では、架空の多国籍企業である Contoso が、組織のチームボイスソリューションを実装する方法についてのケーススタディについて説明します。

Contoso は、ネットワーク、id、Windows 10 Enterprise、Office 365 ProPlus、モバイルデバイス管理、情報保護、セキュリティ、Skype for Business から Teams、電話システム、電話会議へのアップグレードなどの、Microsoft 365 Enterprise を展開し、主要設計上の決定と実装の詳細を展開しています。  

この記事では、Contoso がオンプレミスユーザーをチームに移行して、統合されたコミュニケーション、コラボレーション、および音声を実現する方法について説明します。 Contoso が Microsoft のクラウドサービスを使用してデジタル変換を加速する方法についての背景情報については、「 [contoso のケーススタディの概要」](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide)から始まるすべての主要な記事を参照してください。

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

主要な記事には、次の情報が記載されています。  

- Contoso の IT インフラストラクチャのニーズ
- 用
- Identity
- Windows 10 Enterprise
- Office 365 Pro Plus
- モバイルデバイス管理
- 情報の保護
- Microsoft 365 エンタープライズセキュリティの概要
- トップ機密プロジェクトのチーム
- 機密性の高いデジタル資産用の SharePoint Online サイト

アップグレードの計画については、「 [Microsoft Teams のアップグレードを開始](upgrade-start-here.md)する」を参照してください。

## <a name="contoso-business-goals-for-teams"></a>チーム向けの Contoso のビジネス目標

オンプレミスのコミュニケーション、共同作業、および音声のためにチームに移行するために、Contoso は次のビジネス目標を決定しました。

- Teams の有効化 

  セキュリティで保護された内部と外部のコラボレーションを管理して有効にするための適切なポリシーを備えた、Contoso の統合されたコミュニケーションとコラボレーションチーム。 

- Skype for Business から Teams へのアップグレード 

  Skype for Business は Contoso 内で広く展開されました。 従来のシステムから移行する必要があるため、Contoso は、Skype for Business ユーザーを Teams にアップグレードすることを決定しました。 詳細については、「 [Contoso のケーススタディ: Teams アップグレード計画](voice-case-study-migration-plan.md)」を参照してください。

- 電話システム  

  エンタープライズ voip での Skype for Business は、Contoso 内で広く展開されました。 仲介サーバーの次ホップであったレガシシステムをオフにする必要がある場合、Contoso は Skype for Business エンタープライズボイスユーザーを電話システムに移行しました。 Contoso サイトでは、Microsoft 通話プラン、電話システムダイレクトルーティング、または両方の組み合わせを使用しました。 詳細については、「 [Contoso のケーススタディ: 電話システム](voice-case-study-phone-system.md)」を参照してください。

- 場所に基づくルーティング 

  Office の所在地が電話で規制されている国の場合、Contoso は、電話システムの展開時に Skype for Business に含まれていた場所に基づくルーティングを再作成する必要がありました。 詳細については、「 [Contoso のケーススタディ: 位置情報に基づくルーティング](voice-case-study-location-based-routing.md)」を参照してください。

- 緊急通話 

  直接ルーティングが実装されている場合、Contoso は承認されたサードパーティとの緊急電話を設定します。 詳細については、「 [Contoso のケーススタディ: 緊急通話](voice-case-study-emergency-calling.md)」を参照してください。

- 電話会議 

  Contoso は、SIP トランクでホストされていた電話会議サービス番号を PSTN プロバイダーに設定します。 詳細については、「 [Contoso のケーススタディ: 電話会議](voice-case-study-audio-conferencing.md)」を参照してください。 

- ローカルメディアの最適化 

  Contoso は、リモートサイトで利用されていた1つの直接ルートトランクが Microsoft 電話システムにある場所で、ローカルメディア最適化を利用しました。 詳細については、「[ローカルメディア最適化の計画](direct-routing-media-optimization.md)」および「[ローカルメディア最適化の構成](direct-routing-media-optimization-configure.md)」を参照してください。

- 自動応答と通話キュー

  Covid-19 の結果として、Contoso は、スタッフがリモートで作業している間、受付サポートを提供することを希望していました。 Contoso は自動応答と通話キューを使って、受付者の電話番号への着信通話を管理していました。 詳細については、「 [Contoso のケーススタディ: 自動応答と通話キュー](voice-case-study-call-queues.md)」を参照してください。  


