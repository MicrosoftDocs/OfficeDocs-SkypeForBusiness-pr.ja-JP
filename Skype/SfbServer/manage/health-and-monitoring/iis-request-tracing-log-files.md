---
title: Skype for Business Server 2015 での IIS 要求トレース ログ ファイルの監視
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: '概要: は、レガシ クライアントのサーバー 2015 のビジネスをサポートするため、Skype では、モビリティ サービス (Mcx) について説明します。'
ms.openlocfilehash: 51913162603203333cd201c64ed21770825bdaf7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での IIS 要求トレース ログ ファイルの監視
 
**の概要:**ビジネス サーバー 2015 のレガシ クライアントをサポートするため、Skype では、モビリティ サービス (Mcx) について説明します。
  
このトピックは、Lync 2010 Lync Mobile クライアントをサポートする展開のみに適用され、Mobility Service (Mcx) を対象としています。
  
Skype のインターネット インフォメーション サービス (IIS) の要求のトレースを有効にビジネス サーバー移動サービス (Mcx) のときに生成されるログ ファイルは最大 3 ギガバイトの空き容量が 1 日を使用できます。 IIS トレース ログは既定で有効になります。 ディスクの空き領域が不足実行されないことになっていることを確認するのにはフロント エンド サーバーを監視する必要があります。 
  
既定では、IIS はログ ファイルを %SystemDrive%\inetpub\logs\LogFiles に格納します。
  
サーバー全体で IIS 要求トレースをオフにするには、コマンド ラインで次のように入力します。
  
```
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

詳細については、 **httpLogging**コマンドは、[コマンドのリファレンス](https://go.microsoft.com/fwlink/p/?linkId=234927)を参照してください。
  

