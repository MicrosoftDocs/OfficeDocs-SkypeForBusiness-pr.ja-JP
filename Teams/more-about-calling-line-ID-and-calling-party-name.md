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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
ms.service: msteams
description: 通話回線 ID と発信側の名前について説明します。
ms.openlocfilehash: 13167e41a5e104e198c557af90ed121e90abcf55
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617243"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a>発信回線 ID と発信者名の詳細

CallerID は、次の 2 つのユーザー向け情報で構成されます。

- 電話番号 (通常は CLID または通話回線 ID と呼ばれます)。

- 発信者名 (通常は CNAM と呼ばれます)。 

呼び出しが行われると、CLID (電話番号) は宛先の通信事業者 (終端の通信事業者とも呼ばれます) にルーティングされます。 この情報は国がどのように CNAM を実装したかに依存するため、呼び出しの CNAM 情報は呼び出しと共にルーティングされる場合とルーティングされない場合があります。 通話に対する CNAM 配信の信頼性は、通話を処理する国と運送業者によって異なります。仲介者または終了側の運送業者のいずれかです。 

CNAM 転送& CLID は、終端側のキャリアの責任です。 終端の通信事業者は、CLID & CNAM 機能をサポートするだけでなく、両方の値に対して最新のレコードを提供する必要があります。 Microsoft は呼び出しの発信時に CLID 値を確実に提供しますが、中間の通信事業者または終端の通信事業者を通過した場合、これらの値はそのまま保持されない場合があります。 CLID 値が中間者または終端の運送業者によって変更、省略、または切り捨てられた場合、Microsoft は公衆電話網でこのような問題を修正することはほとんどありません。

CNAM の不整合は、中間または終端の通信事業者が、信頼できるデータベースの CNAM 情報の更新を遅らせるときに発生する可能性があります。米国の場合と同様です。 CNAM に対して信頼できるデータベースがない国では、個々の運送業者のプラクティスによって、通話で CNAM 情報がそのまま到着する際に問題が発生する可能性もあります。 Microsoft は現在、米国以外の国の発信 CNAM 情報をサポートしていません。

## <a name="related-topics"></a>関連項目


