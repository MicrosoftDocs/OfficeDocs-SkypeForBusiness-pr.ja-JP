---
title: "Skype for Business と Microsoft Teams の連携 | Microsoft サポート"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: overview
ms.service: msteams
description: "チャットや通話など、Skype for Business と Microsoft Teams の連携について説明します。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 02d11632a0a6b8f78504ab20ae3415a942e6c91f
ms.sourcegitcommit: 9e217129451afae32eb3cd27fb3ee591874c29c9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
<a name="how-skype-for-business-and-microsoft-teams-interact"></a>Skype for Business と Microsoft Teams の連携
===================================================

組織で Skype for Business を使用している場合、Skype for Business と Microsoft Teams がどのように連携するかを理解することは重要です。

一般的に配布されている Microsoft Teams では、Microsoft Teams と Skype for Business Online または Hybrid の基本的な相互運用性は、ピアツーピア (P2P) のインスタント メッセージングのみです。

既定の動作では、Microsoft Teams クライアントは Microsoft Teams のバックエンド サービスと Skype for Business サービスの両方にサインインします (デュアルスタック アプローチ)。Microsoft Teams クライアントは Skype for Business に対して IM 機能のみを提示するため、Skype for Business から Microsoft Teams ユーザーを検索すると、そのユーザーは「IM のみ」として表示されます。次の例では、Alix Wilber は Microsoft Teams クライアントのみにサインインしています。

![](media/Understand_how_Skype_for_Business_and_Microsoft_Teams_interact_image1.png)

Microsoft Teams では、ユーザーは現在 Skype for Business のみが有効になっている組織内のユーザーを検索でき、そのユーザーとインスタント メッセージングによるチャット セッションを行うことができます。

Skype for Business のユーザーは、Microsoft Teams のチャット ウィンドウに受信したインスタント メッセージに返信できます。

![](media/Understand_how_Skype_for_Business_and_Microsoft_Teams_interact_image2.png)

Microsoft Teams のユーザーは、Skype for Business でも有効になっている場合は、それぞれに対応するクライアントを同時に使用して Microsoft Teams と Skype for Business にサインインできます。

最後にアクティブであったエンドポイントが優先されるため、ユーザーが Microsoft Teams を積極的に使用している場合、Skype for Business ユーザーが送信したインスタント メッセージは Microsoft Teams チャット ウィンドウで受信します。ユーザーが Skype for Business を使用して通話の着信や発信を行っている場合や Skype for Business での通話を終えたばかりの場合に Microsoft Teams クライアントに戻っていなければ、Skype for Business が最近のアクティブなエンドポイントとなるため、Skype for Business ユーザーが送信したインスタント メッセージは Skype for Business クライアントで受信します。

現時点では、Microsoft Teams は Skype for Business に対してピアツーピア (P2P) インスタント メッセージングの相互運用性しかサポートしません。そのため、Skype for Business ユーザーからの一切の音声/ビデオの通話、Skype for Business 会議への招待はその形式に関わらず Skype for Business クライアントのみで受信します。Microsoft Teams クライアントからの一切の音声/ビデオの通話、グループ通話への招待はその形式に関わらず Microsoft Teams クライアントのみで受信します。

上記の動作により、Microsoft Teams と Skype for Business を同時に使用しても操作の快適性が確保され、エンドユーザーは適切なツールを使って特定の通信を処理できます。ただし、相互運用性の仕組みとそれがエンドユーザーのエクスペリエンスに与える影響を理解するには、エンドユーザーの正しい知識が必要になります。


|  |  |
|---------|---------|
|![](media/Understand_how_Skype_for_Business_and_Microsoft_Teams_interact_image3.png)<br>注意</br>      |Skype for Business との相互運用において、Teams で受信するインスタント メッセージは Skype for Business 会話履歴に記録されません。         |

Microsoft Teams では、[通知] 設定で Skype for Business との相互運用を無効にする機能が提供されています。この設定はユーザー制御が可能であるため、各ユーザーは動作を任意に決定することができます。
