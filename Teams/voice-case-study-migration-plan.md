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
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 多国籍企業向け Teams 音声ケース スタディ
appliesto:
- Microsoft Teams
ms.openlocfilehash: 93f6d0877537a740dc867b44c3c4deb9bebb8441
ms.sourcegitcommit: 6f7b91f573e2a034f8c5474be2c5cb2971f4b5ab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421292"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a>Contoso のケース スタディ: Teams アップグレード プラン

Skype for Business から Teams に移行する決定で、Contoso はエンド ユーザーに簡単な移行エクスペリエンスを提供する必要があります。 全員を同時に Teams に切り替える代わりに、ハイブリッド接続をセットアップし、重複する機能の方法を使用してユーザーを Teams に移動することを決定しました。 これにより、Teams と Skype for Business オンプレミスのユーザーはプレゼンスを共有し、通信を行う必要がありました。 ユーザーが電話システムのパイロットに参加すると、ユーザーは Teams のみモードに移動されました。

アップグレード、メソッド、モードに関する基本的な概念を理解するために、Contoso は次の記事を読んで説明します。

- [Microsoft Teams へのアップグレードを開始する](upgrade-start-here.md)
- [IT 管理者向けアップグレード戦略](upgrade-to-teams-on-prem-implement.md) 
- 詳細については、「[移行と相互運用に関するガイドライン](migration-interop-guidance-for-teams-with-skype.md)」を参照してください。
 
Contoso は、Skype for Business から Teams へのパスを設計する Ignite 2019 [セッションにも参加しました](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions)。 Contoso は次の情報を学習しました。

- 相互運用性、フェデレーション、アップグレード動作などの基本的な概念 

- TeamsUpgradePolicy に基づく共存モードと管理 

- エンド ユーザー エクスペリエンス: 

  - チャットと通話 

  - 会議のスケジュール 

  - Teams クライアントでのコラボレーション機能の可用性 

ハイブリッド接続を計画および構成するには、オンプレミス環境をクラウドに移行する最初の手順として、Contoso はハイブリッド[](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)接続を計画し、[](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)次の方法を理解するためにハイブリッド接続を構成します。 

  - オンプレミス環境サービスを構成して、Office 365 とフェデレーションします。 

  - オンプレミス環境を構成して Office 365 を信頼し、Office 365 で共有 SIP アドレス空間を有効にする 

  - Office 365 テナントで共有 SIP アドレス空間を有効にします。

  - テクニカル パイロット中は、諸島モードを使用します。

  - ユーザーが電話システムに対して有効になると、ユーザーを TeamsOnly モードに切り替えます。 通話プランと直接ルーティングには TeamsOnly モードが必要です。 
