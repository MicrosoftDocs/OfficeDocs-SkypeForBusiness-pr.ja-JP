---
title: 発信回線 ID と発信者名の詳細
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 新しい電話番号のポート注文ウィザードを使用するときに、アカウントを変更できる認証済みユーザーを追加する必要がある理由について説明します。
ms.openlocfilehash: 833bb27aa34b16601485437be9e25e2e41c2bf4e
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573381"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a>発信回線 ID と発信者名の詳細

CallerID は、一般的に参照されているため、実際には2つのユーザーに対して識別できる情報が含まれています。
    - 電話番号 (通常は CLID または通話回線 ID とも呼ばれます) 
    - 発信者の名前 (通常は CNAM とも呼ばれます) で、最大15文字の長さを指定できます。 

通話が発信されると、CLID (電話番号) は送信先の電話会社 (終了キャリアとも呼ばれます) にルーティングされます。 この方法では、通話の CNAM info が通話と共にルーティングされないことがあります。これは、国が CNAM を実装しているかどうかによって異なります (すべての場合)。 CNAM での通話の信頼性は、通話を発信する国と航空会社によって異なります。中継または終了キャリアとして通話を処理します。 

CLID & CNAM 伝送は、終了キャリアが CLID & CNAM 機能をサポートしており、両方の値の最新のレコードを提供している必要があるため、終了キャリアの責任となります。 Microsoft は、発信時に CLID の値を提供していますが、中継業者または終了キャリアを通過すると、それらの値がそのまま保持されないことがあります。 残念ながら、CLID 値が変更された場合や、中継業者または終了キャリアによって省略または切り捨てられた場合、Microsoft は、このような問題を解決するために、公衆電話網の問題を修正することはほとんどありません。

CNAM の不整合は、米国の場合と同様に、信頼できるデータベースの CNAM 情報を更新するときに、中間または終了キャリアで遅延が発生する可能性があります。 CNAM の権限を持つデータベースが存在しない国では、個々の運送業者の慣行によって、tact で着信した CNAM 情報に関する問題が発生することもあります。 現時点では、Microsoft は米国以外の国での CNAM 情報の送信をサポートしていません。」

## <a name="related-topics"></a>関連項目


