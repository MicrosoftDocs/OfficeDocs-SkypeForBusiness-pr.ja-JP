---
title: Teamsボイス Contoso のケース スタディ アップグレード プラン
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
description: 'Teams多国籍企業向けの音声ケース スタディ: アップグレード計画。'
appliesto:
- Microsoft Teams
ms.openlocfilehash: 39cfd66f0ff34fb0f8792871ddfdcceebb2b9961
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2022
ms.locfileid: "65822986"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a>Contoso のケース スタディ: Teams アップグレード 計画

Skype for BusinessからTeamsに移行するという決定では、Contoso はエンド ユーザーに簡単な移行エクスペリエンスを提供したいと考えていました。 全員を同時にTeamsに切り替える代わりに、ハイブリッド接続を設定し、重複する機能メソッドを使用してユーザーをTeamsに移動することにしました。 これにより、オンプレミスのTeamsとSkype for Businessのユーザーがプレゼンスを共有し、通信することができました。 ユーザーが電話システムのパイロットに入ると、Teamsのみモードに移行されました。

アップグレード、メソッド、モードに関する基本的な概念を理解するために、Contoso は次の記事を読みます。

- [Microsoft Teams へのアップグレードを開始する](upgrade-start-here.md)
- [IT 管​​理者向けのアップグレード戦略](upgrade-to-teams-on-prem-implement.md) 
- 詳細については、「[移行と相互運用に関するガイドライン](migration-interop-guidance-for-teams-with-skype.md)」を参照してください。
 
Contoso は、Ignite 2019 セッションに参加しました[。Skype for BusinessからTeamsへのパスの設計](https://myignite.microsoft.com/archives/IG20-OD251)も行いました。 Contoso は次について学習しました。

- 相互運用性、フェデレーション、アップグレード動作などの基本的な概念 

- TeamsUpgradePolicy に基づく共存モードと管理 

- エンド ユーザー エクスペリエンス: 

  - チャットと通話 

  - 会議のスケジュール 

  - Teams クライアントでのコラボレーション機能の可用性 

ハイブリッド接続を計画して構成するには、オンプレミス環境をクラウドに移行する最初の手順である Contoso の「 [ハイブリッド接続の計画」と「ハイブリッド接続](/SkypeForBusiness/hybrid/plan-hybrid-connectivity) の [構成」](/SkypeForBusiness/hybrid/configure-hybrid-connectivity) を参照して、次の方法を理解します。 

  - Office 365とフェデレーションするようにオンプレミス環境サービスを構成します。 

  - Office 365を信頼し、Office 365で共有 SIP アドレス空間を有効にするようにオンプレミス環境を構成する 

  - Office 365 テナントで共有 SIP アドレス空間を有効にします。

  - 技術パイロットの間にアイランド モードを使用します。

  - ユーザーが電話システムに対して有効になったら、ユーザーを TeamsOnly モードに切り替えます。 通話プランとダイレクト ルーティングには TeamsOnly モードが必要です。
