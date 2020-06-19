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
ms.openlocfilehash: d5429b4c45ccea82d1451210438bedd328618604
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786092"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a>Contoso のケーススタディ: Teams アップグレード計画

Skype for Business から Teams への移行を決定する際に、Contoso はエンドユーザー向けの簡単な切り替えエクスペリエンスを提供する必要がありました。 全員を同時に Teams に切り替えるのではなく、ハイブリッド接続を設定し、重複する機能のメソッドを使用してユーザーを Teams に移動することにしました。 これにより、チームと Skype for Business のオンプレミスのユーザーがプレゼンスを共有して通信できるようになりました。 ユーザーが電話システムのパイロットを入力すると、そのユーザーは [Teams のみ] モードに移動されました。

アップグレード、方法、およびモードに関する基本概念を理解するために、Contoso は次の記事を参照してください。

- [Microsoft Teams へのアップグレードを開始する](upgrade-start-here.md)
- [Skype for Business から Teams へのアップグレード](upgrade-to-teams-on-prem-overview.md) 
- [移行と相互運用性のガイダンス](migration-interop-guidance-for-teams-with-skype.md)
 
Contoso は、 [Skype For business から Teams へのパスを設計して](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions)いる Ignite 2019 セッションも参加しています。 Contoso が次のことを学習しました。

- 相互運用性、フェデレーション、アップグレード動作などの基本的な概念 

- TeamsUpgradePolicy に基づく共存モードと管理 

- エンドユーザーエクスペリエンス: 

  - チャットと通話 

  - 会議のスケジュール 

  - チームクライアントのコラボレーション機能の可用性 

ハイブリッド接続を計画して構成するために、最初の手順として、オンプレミス環境をクラウドに移行するには、「[ハイブリッド接続の計画](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)とハイブリッド接続の[構成](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)」を参照して、次の操作を行います。 

  - Office 365 とのフェデレーションを行うために、オンプレミス環境サービスを構成します。 

  - Office 365 を信頼するようにオンプレミス環境を構成して、Office 365 で共有 SIP アドレススペースを有効にする 

  - Office 365 テナントで共有 SIP アドレス空間を有効にします。

  - テクニカルパイロットでは、諸島モードを使用します。

  - ユーザーが電話システムを有効にしている場合は、ユーザーをチームのみに切り替えます。 プランの呼び出しと直接ルーティングを行うには、TeamsOnly モードが必要です。 
