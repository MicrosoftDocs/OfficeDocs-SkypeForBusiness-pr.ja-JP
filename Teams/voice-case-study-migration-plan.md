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
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams企業向け音声ケース スタディ
appliesto:
- Microsoft Teams
ms.openlocfilehash: b0da56bc0da083654a0cd694bd5983f2fe4fe515
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093727"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a>Contoso のケース スタディ: Teams アップグレード プラン

Contoso は、Skype for Business から Teams に移行する決定で、エンド ユーザーに簡単な移行エクスペリエンスを提供したいと思いました。 全員を同時に Teams に切り替える代わりに、ハイブリッド接続を設定し、オーバーラップ機能方式を使用してユーザーを Teams に移動しました。 これにより、オンプレミスのユーザー Teams、Skype for Businessと通信を共有できます。 ユーザーがパイロット モードに入電話システム、ユーザーは [のみ] Teamsに移動されました。

アップグレード、方法、およびモードに関する基本的な概念を理解するために、Contoso は次の記事を読んで説明します。

- [Microsoft Teams へのアップグレードを開始する](upgrade-start-here.md)
- [IT 管理者向けアップグレード戦略](upgrade-to-teams-on-prem-implement.md) 
- 詳細については、「[移行と相互運用に関するガイドライン](migration-interop-guidance-for-teams-with-skype.md)」を参照してください。
 
Contoso は Ignite 2019 セッションに参加しました。このセッションでは、Skype for Business[から Teams。](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions) Contoso は次の情報を学習しました。

- 相互運用性、フェデレーション、アップグレード動作などの基本的な概念 

- TeamsUpgradePolicy に基づく共存モードと管理 

- エンド ユーザー エクスペリエンス: 

  - チャットと通話 

  - 会議のスケジュール 

  - 新しいクライアントでのコラボレーション機能Teams可能 

ハイブリッド接続を計画して構成するには、オンプレミス環境をクラウドに移行する最初の手順として、「ハイブリッド接続の計画[](/SkypeForBusiness/hybrid/plan-hybrid-connectivity)」と「ハイブリッド接続[](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)の構成」を参照して、次の方法を理解します。 

  - オンプレミス環境サービスを構成して、オンプレミスの環境サービスとOffice 365。 

  - オンプレミス環境を構成して、Office 365を信頼し、共有 SIP アドレス空間を有効Office 365 

  - 自分のテナントで共有 SIP アドレス空間Office 365します。

  - テクニカル パイロット中は、Islands モードを使用します。

  - ユーザーが TeamsOnly モードに切り替える場合は、ユーザーが有効になっていると電話システム。 通話プランと直接ルーティングには TeamsOnly モードが必要です。