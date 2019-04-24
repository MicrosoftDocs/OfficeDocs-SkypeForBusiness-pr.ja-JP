---
title: Skype for Business Server 2015 での IIS 要求トレース ログ ファイルの監視
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: '概要: は、レガシ クライアントのサーバー 2015 のビジネスをサポートするため、Skype では、モビリティ サービス (Mcx) について説明します。'
ms.openlocfilehash: 6c885c441531dc02e149ee1fb37f0001d252811f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199685"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での IIS 要求トレース ログ ファイルの監視
 
**の概要:** ビジネス サーバー 2015 のレガシ クライアントをサポートするため、Skype では、モビリティ サービス (Mcx) について説明します。
  
このトピックは、Lync 2010 Lync Mobile クライアントをサポートする展開のみに適用され、Mobility Service (Mcx) を対象としています。

> [!NOTE]
> 従来のモバイル クライアント用の MCX (移動サービス) サポートがビジネス サーバー 2019 の Skype で利用可能ではありません。 ビジネスのモバイル クライアントのすべての現在 Skype は、インスタント メッセージング (IM)、プレゼンス、および取引先担当者をサポートするために既にユニファイド コミュニケーション Web API (UCWA) を使用します。 MCX を使用する従来のクライアントを持つユーザーは、現在のクライアントにアップグレードする必要があります。
  
Skype のインターネット インフォメーション サービス (IIS) の要求のトレースを有効にビジネス サーバー移動サービス (Mcx) のときに生成されるログ ファイルは最大 3 ギガバイトの空き容量が 1 日を使用できます。 IIS トレース ログは既定で有効になります。 ディスクの空き領域が不足実行されないことになっていることを確認するのにはフロント エンド サーバーを監視する必要があります。 
  
既定では、IIS はログ ファイルを %SystemDrive%\inetpub\logs\LogFiles に格納します。
  
サーバー全体で IIS 要求トレースをオフにするには、コマンド ラインで次のように入力します。
  
```
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

詳細については、 **httpLogging**コマンドは、[コマンドのリファレンス](https://go.microsoft.com/fwlink/p/?linkId=234927)を参照してください。
  

