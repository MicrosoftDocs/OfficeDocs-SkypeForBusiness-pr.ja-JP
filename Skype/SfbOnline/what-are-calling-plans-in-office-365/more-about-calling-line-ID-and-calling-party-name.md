---
title: 明細行 ID を呼び出すと関係者の名前を呼び出すことについて
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 新しいローカル番号のポートの注文ウィザードを使用すると、アカウントに変更を加える権限を持つ人を追加する必要がある理由について説明します。
ms.openlocfilehash: 1174ba5837bb91c3251232ab48fa63c343425ac1
ms.sourcegitcommit: f942232d43fc4ad56b34dd400fdb4bca39013f5f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a>明細行 ID を呼び出すと関係者の名前を呼び出すことについて

発信者番号、参照されている通常、実際にで構成されます情報のユーザーに接続する特定の 2 つの要素。
    - (CLID または通話とライン ID と通常呼ばれる) 電話番号 
    - 15 文字までの長さは、関係者名 (一般的には CNAM と呼ばれます) を呼び出しています。 

呼び出しが行われた、CLID (電話番号) にリンク先の配送業者 (終端キャリアとも呼ばれます) にルーティングされます。 CNAM の呼び出しの情報は、この実装によって異なりますどの国が CNAM (ある場合) と、呼び出しにルーティングされません可能性があります。 呼び出しに CNAM の配信の信頼性は、国との中間層として、その呼び出しを処理する通信事業者または終端のキャリアによって異なります。 

CLID と CNAM の転送は、終端のキャリア必要があります CLID と CNAM の機能のサポートし、値の両方の最新レコードを提供するような終端の通信事業者の責任です。 呼び出しを発信するときに Microsoft が CLID 値に確実に提供しますが、これらの値が保つことができませんそのままの状態、中間のキャリアまたは終端のキャリアを通過すると。 残念ながら、CLID 値は、変更またはを省略すると、中間または末尾のキャリアでは切り捨てられ、イベント、マイクロソフトには、公衆電話網では、このような問題を修正するをほとんどの型がありません。

CNAM で不整合への可能性が米国の場合のように権限を持つデータベースに CNAM の情報を更新する中間または末尾のキャリアに遅延が発生します。 国に CNAM の権限を持つデータベースが存在しない、個々 のキャリア ・ プラクティスも問題があります CNAM の情報の整合性を呼び出しに到着したとします。 Microsoft 現在サポートしていません CNAM の発信元の情報、米国以外の国々 で。」

## <a name="related-topics"></a>このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。


