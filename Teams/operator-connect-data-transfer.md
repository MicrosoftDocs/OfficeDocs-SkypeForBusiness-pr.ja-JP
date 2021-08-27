---
title: オペレーター サービスを利用した運送業者と Microsoft の間でのConnect
author: MicrosoftHeidi
ms.author: heidip
ms.reviewer: alaina, creager
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 通信事業者と Microsoft との間でのデータまたは情報の転送に関する特定のプライバシー情報(特にオペレーターとオペレーターとの関係) Connect。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 851d04b3e0d24af7a31b820c812046c55fad21f1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582191"
---
# <a name="data-transfers-between-carriers-and-microsoft-for-operator-connect"></a>オペレーター サービスを利用した運送業者と Microsoft の間でのConnect

## <a name="provisioned-and-assigned-numbers"></a>プロビジョニング済みおよび割り当て済み番号

オペレーター Connect プログラムが適切に機能することを保証するために、Microsoft は API を通じて、各参加している通信事業者に通知します。この API は、Teams 管理センター内で割り当てられている携帯電話会社の電話番号と、その電話番号の SIP URI (Session Initiation Protocol Uniform Resource Identifiers) を通じて割り当て済みです。

## <a name="call-detail-records-and-quality-data"></a>通話詳細レコードと品質データ

Microsoft は、API を通じて各参加通信事業者に通話の詳細レコードと品質データを提供します。 これは、Microsoft と通信事業者がトラブルシューティングを実行し、サービスの適切な機能を確保するために必要です。

## <a name="call-duration-data"></a>通話時間データ

各通信事業者は、API を通じて、お客様がサービス を使用して行った呼び出しのMicrosoft Teams。 Microsoft は、これらのレコードを使用して、お客様に使用状況情報を提供し、Microsoft のレコードが運送業者のレコードと一致する必要があります。 Microsoft は、適用される法令および Microsoft のプライバシーに関する声明に従って、これらのレコードを保存および処理します。

詳細については、「購入、構成、有効にする」を参照[キャリア コーチをMicrosoft Teams](career-coach.md)
