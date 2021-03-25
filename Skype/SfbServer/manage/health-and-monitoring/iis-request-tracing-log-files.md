---
title: Skype for Business Server 2015 での IIS 要求トレース ログ ファイルの監視
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: '概要: 従来のクライアントに対する Skype for Business Server 2015 サポートのモビリティ サービス (Mcx) について説明します。'
ms.openlocfilehash: 7d0d15b4c3db3d768117d73ed610b38c7a819196
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118636"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での IIS 要求トレース ログ ファイルの監視
 
**概要:** 従来のクライアントに対する Skype for Business Server 2015 サポートのモビリティ サービス (Mcx) について説明します。
  
このトピックは、Lync 2010 Lync Mobile クライアントのみをサポートする展開に適用され、モビリティ サービス (Mcx) を対象としています。

> [!NOTE]
> 従来のモバイル クライアントの MCX (モビリティ サービス) サポートは、Skype for Business Server 2019 では利用できなくなりました。 現在のすべての Skype for Business モバイル クライアントはUnified Communications Web API (UCWA) を使用して、インスタント メッセージング (IM)、プレゼンス、および連絡先をサポートしています。 MCX を使用している従来のクライアントを持っているユーザーは、現在のクライアントにアップグレードする必要があります。
  
Skype for Business Server Mobility Service (Mcx) のインターネット インフォメーション サービス (IIS) 要求トレースを有効にすると、生成されるログ ファイルは 1 日に最大 3 ギガバイトのディスク領域を消費できます。 IIS トレース ログは既定で有効になっています。 フロント エンド サーバーを監視して、ディスク領域が使い切れなか確認する必要があります。 
  
既定では、IIS はログ ファイルを %SystemDrive%\inetpub\logs\LogFiles に格納します。
  
サーバー全体で IIS 要求トレースをオフにするには、コマンドラインで、次のように入力します。
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

**httpLogging** コマンドの詳細については、コマンド リファレンス [を参照してください](/previous-versions/iis/settings-schema/aa347466(v=vs.90))。
