---
title: 2015 年に常設チャット データベースをバックアップSkype for Business Serverする
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: '概要: 2015 年に常設チャット サーバー データベースをバックアップおよび復元するSkype for Business Serverします。'
ms.openlocfilehash: 0f875fd62eab26873b8dcc3617de709a397f4ba8
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60762345"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a>2015 年に常設チャット データベースをバックアップSkype for Business Serverする
 
**概要:** 2015 年に常設チャット サーバー データベースをバックアップおよび復元するSkype for Business Serverします。
  
常設チャット サーバーでは、SQL Serverコンテンツ、構成、ユーザー プロビジョニング、その他の関連するメタデータなどのチャット ルーム データを格納するために、データベース ソフトウェアを使用する必要があります。 さらに、組織に常設チャット アクティビティをアーカイブする必要がある規制がある場合、オプションのコンプライアンス サービスが有効になっている場合は、SQL Server データベース ソフトウェアを使用して、チャット コンテンツやイベント (会議室への参加や退室など) を含むコンプライアンス データを格納します。 チャット ルームのコンテンツは常設チャット データベース (mgc) に格納されます。 コンプライアンス データはコンプライアンス データベース (mgccomp) に格納されます。 これは、定期的にバックアップする必要があるビジネスクリティカルなデータです。 
  
> [!NOTE]
> 常設チャットは 2015 Skype for Business Serverで使用できますが、2019 年Skype for Business Serverではサポートされていません。 同じ機能は、Teams。 詳細については、「アップグレードの開始[方法」をMicrosoft Teamsしてください](/microsoftteams/upgrade-start-here)。 常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、2015 年Skype for Business Serverします。 

## <a name="back-up-the-databases"></a>データベースのバックアップ

常設チャット データをバックアップするには、2 つの方法があります。 
  
- SQL Serverバックアップ
    
- 常設チャット データをファイルとしてエクスポートする **Export-CsPersistentChatData** コマンドレット
    
SQL Server バックアップを使用して作成されるデータには **、Export-CsPersistentChatData** コマンドレットによって作成されたディスク領域の 20 倍のディスク領域が必要になりますが、SQL Server バックアップは使い慣れた手順である可能性があります。
  
バックアップ手順を使用するSQL Server詳細については、SQLドキュメントを参照してください。 
  
**Export-CsPersistentChatData** コマンドレットを使用する場合は、次のようにコマンドを指定できます。
  
```PowerShell
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

または
  
```PowerShell
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

たとえば、次のコマンドは、サーバー サーバー上にある常設チャット データベースから常設チャット データをエクスポート atl-sql-001.contoso.com。エクスポートされたデータは、ファイル に保存C:\Logs\PersistentChatData.zip。 Level パラメーターが指定されていないので、コマンドは常設チャット情報を完全にエクスポートします。
  
```PowerShell
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a>データベースを復元する

常設チャット データを復元する方法は、バックアップに使用した方法によって異なります。 バックアップ手順をSQL Server場合は、復元手順SQL Server使用する必要があります。 **Export-CsPersistentChatData** コマンドレットを使用して常設チャット データをバックアップした場合は **、Import-CsPersistentChatData** コマンドレットを使用してデータを復元する必要があります。
  
```PowerShell
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

または
  
```PowerShell
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
