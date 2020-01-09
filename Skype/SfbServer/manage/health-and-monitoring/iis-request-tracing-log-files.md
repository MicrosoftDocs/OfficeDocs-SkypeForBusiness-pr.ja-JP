---
title: Skype for Business Server 2015 での IIS 要求トレース ログ ファイルの監視
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: '概要: Skype for Business Server 2015 のモバイルサービス (Mcx) とレガシクライアントのサポートについて説明します。'
ms.openlocfilehash: f519a04f878caf953c54873a6a704232245b344b
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992182"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での IIS 要求トレース ログ ファイルの監視
 
**概要:** レガシクライアント向けの Skype for Business Server 2015 サポートのモバイルサービス (Mcx) について説明します。
  
このトピックは、Lync 2010 Lync Mobile クライアントをサポートする展開のみに適用され、Mobility Service (Mcx) を対象としています。

> [!NOTE]
> Skype for Business Server 2019 では、従来のモバイルクライアントに対する MCX (モバイルサービス) のサポートは利用できなくなりました。 現在のすべての Skype for Business のモバイルクライアントでは、インスタントメッセージング (IM)、プレゼンス、連絡先をサポートするために、既にユニファイドコミュニケーション Web API (UCWA) を使用しています。 MCX を使用するレガシクライアントを使っているユーザーは、現在のクライアントにアップグレードする必要があります。
  
Skype for Business Server Mobility Service (Mcx) のインターネットインフォメーションサービス (IIS) 要求トレースを有効にすると、生成されるログファイルは1日に最大 3 gb のディスク領域を消費する可能性があります。 IIS トレースログは既定で有効になっています。 フロントエンドサーバーを監視して、ディスク領域が不足していないことを確認する必要があります。 
  
既定では、IIS はログ ファイルを %SystemDrive%\inetpub\logs\LogFiles に格納します。
  
サーバー全体で IIS 要求トレースをオフにするには、コマンド ラインで次のように入力します。
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

**HttpLogging**コマンドの詳細については、[コマンドリファレンス](https://go.microsoft.com/fwlink/p/?linkId=234927)を参照してください。
  

