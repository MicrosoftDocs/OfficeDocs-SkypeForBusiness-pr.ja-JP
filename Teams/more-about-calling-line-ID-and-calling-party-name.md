---
title: 発信回線 ID と発信者名の詳細
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: roykuntz, jenstr
ms.topic: article
ms.tgt.pltfrm: cloud
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business Online
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
ms.service: msteams
description: 通話回線 ID と通話者名について説明します。
ms.openlocfilehash: dd68327c8fb3f63bf17e0736f9d41b727efc1ff8
ms.sourcegitcommit: 83f14c4c79559ef28357ff076938e52b369fc0c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2021
ms.locfileid: "52308316"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a>発信回線 ID と発信者名の詳細

CallerID は、次の 2 つのユーザー向け情報で構成されます。

- 電話番号 (通常は CLID または通話回線 ID と呼ばれます)。

- 呼び出し元のパーティー名 (通常は CNAM と呼ばれます)。 

呼び出しが行われた場合、CLID (電話番号) は宛先の運送業者 (終端通信事業者とも呼ばれる) にルーティングされます。 この情報は国が CNAM を実装した方法に依存する (ある場合) ため、呼び出しの CNAM 情報は呼び出しでルーティングされる場合とルーティングされない場合があります。 呼び出しによる CNAM 配信の信頼性は、通話を処理する国と通信事業者によって異なります。仲介者または終了運送業者のいずれかです。 

CLID & CNAM 送信は、終端の通信事業者の責任です。 終端の通信事業者は、CNAM & CLID をサポートし、両方の値に対して最新のレコードを提供する必要があります。 Microsoft は呼び出しを発信するときに CLID 値を確実に提供しますが、仲介業者または終端の通信事業者を通過すると、それらの値はそのまま保持されない可能性があります。 CLID の値が仲介業者または終端の運送業者によって変更、省略、または切り捨てられた場合、Microsoft は公衆電話ネットワークでこのような問題を修正する方法はほとんど何もありません。

CNAM の不整合は、米国の場合と同様に、中間または終了の通信事業者が権限のあるデータベースの CNAM 情報の更新を遅らせた場合に発生する可能性があります。 CNAM の権限のあるデータベースがない国では、個々の運送業者のプラクティスによって、CNAM 情報が呼び出しと同じ状態で到着する際に問題が発生する可能性があります。 Microsoft は現在、米国以外の国で発信元の CNAM 情報をサポートしていない。

## <a name="related-topics"></a>関連トピック


