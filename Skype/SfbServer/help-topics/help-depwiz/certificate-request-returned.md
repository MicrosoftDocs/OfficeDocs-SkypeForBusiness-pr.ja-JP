---
title: 証明書要求 (結果)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/1/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
description: '[オンライン証明書要求の状態] ページには、オンライン証明書要求を適切に作成および発行した結果として、重要な情報が表示されます。 このページには、証明書を一意に識別する証明書の拇印が表示されます。 既定では、[証明書の使用状況にこの証明書を割り当Skype for Business Server] チェック ボックスがオンになっています。 [完了] をクリックすると、証明書要求の作成手順で定義した目的で、証明書が Lync Server 2013 に自動的に割り当てられます。 既定では、証明書を割り当てる目的は次のとおりです。'
ms.openlocfilehash: e87e16f79a30aa037ba0a7ee3e9ad1379536ca6e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58616093"
---
# <a name="certificate-request-returned"></a>証明書要求 (結果)
 
[**オンライン証明書要求の状態**] ページには、オンライン証明書要求を適切に作成および発行した結果として、重要な情報が表示されます。 このページには、証明書を一意に識別する証明書の拇印が表示されます。 既定では、[この証明書を割り当てる] チェック ボックス **がオンSkype for Business Serverに** 割り当てる] チェック ボックスがオンになっています。 [完了] **をクリック** すると、証明書要求の作成手順で定義した目的で、証明書が Lync Server 2013 に自動的に割り当てられます。 既定では、証明書を割り当てる目的は次のとおりです。
  
- 相互トランスポート層セキュリティ (MTLS) のサーバーの既定 - クライアントおよび他のサーバーへの接続
    
- Web サービスの内部 - トランスポート層セキュリティ/セキュリティ管理 (TLS/SSL) 用の内部 Web サービス サイトSecure Sockets Layerサーバー接続
    
- Web サービスの外部 - TLS/SSL 用の外部 Web サービス サイト上のクライアント接続とサーバー接続
    
[**証明書の詳細の表示**] をクリックすると、証明書を表示して、証明書のプロパティが正しい内容になっていることと、証明書を適用してサーバーで使用できる状態になっていることを確認できます。
  
[**完了**] をクリックすると、オンライン証明書要求プロセスが完了します。 [この証明書を割り当てる] チェック ボックスをオンSkype for Business Server **証明書** の使用状況に割り当てると、証明書が自動的に割り当てられます。 このチェック ボックスをオフにした場合は、別の手順で証明書を割り当てる必要があります。 
  
> [!IMPORTANT]
> 発行元証明機関 (CA) ルート証明書がコンピューターの信頼されたルート証明機関ストアに含されていない場合、または中間 CA 証明書が適切なストアに含されていない場合は、次の図に示す概要の状態が表示されます。 証明書を割り当てるためのオプションはありません。 証明書の割り当てプロセスを完了するには、発行元の CA のルート証明書と任意の中間 CA 証明書をインポートし、メインの [証明書ウィザード] ページで [**割り当て**] をクリックして証明書を割り当てる必要があります。
  

