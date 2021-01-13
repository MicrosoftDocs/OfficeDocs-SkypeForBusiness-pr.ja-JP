---
title: Skype for Business Server 2015 での常設チャット データベースのバックアップと復元
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: '概要: Skype for Business Server 2015 で常設チャット サーバー データベースをバックアップおよび復元する方法について学習します。'
ms.openlocfilehash: 2c99f5e955756020f68b51ea214858c23fee0a48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826377"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での常設チャット データベースのバックアップと復元
 
**概要:** Skype for Business Server 2015 で常設チャット サーバー データベースをバックアップおよび復元する方法について学習します。
  
常設チャット サーバーでは、SQL Serverコンテンツ、構成、ユーザー プロビジョニング、その他の関連するメタデータなどのチャット ルーム データを格納するために、データベース ソフトウェアを使用する必要があります。 また、組織に常設チャットアクティビティのアーカイブを要求する規制がある場合、オプションのコンプライアンス サービスが有効になっている場合、チャット コンテンツやイベント (ルームへの参加や退出など) を含むコンプライアンス データを格納するために SQL Server データベース ソフトウェアが使用されます。 チャット ルームのコンテンツは、常設チャット データベース (mgc) に格納されます。 コンプライアンス データは、コンプライアンス データベース (mgccomp) に格納されます。 これはビジネスに不可欠なデータで、定期的にバックアップする必要があります。 
  
> [!NOTE]
> 常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 Teams でも同じ機能を使用できます。 詳細については、「Microsoft Teams のアップグレード [の開始」を参照してください](/microsoftteams/upgrade-start-here)。 常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかのどちらかを選択できます。 

## <a name="back-up-the-databases"></a>データベースをバックアップする

常設チャット データをバックアップするには、2 つの方法があります。 
  
- SQL Server バックアップ
    
- **Export-CsPersistentChatData** コマンドレット。常設チャットのデータをファイルとしてエクスポートします。
    
SQL Server バックアップを使用して作成されるデータには **、Export-CsPersistentChatData** コマンドレットによって作成されたディスク領域よりも大幅に多くのディスク領域 (場合によっては 20 倍) が必要ですが、SQL Server バックアップは使い慣れた手順である可能性があります。
  
バックアップ手順を使用するSQL Server詳細については、SQLドキュメントを参照してください。 
  
**Export-CsPersistentChatData** コマンドレットを使用する場合は、次のようにコマンドを指定できます。
  
```PowerShell
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

または
  
```PowerShell
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

たとえば、次のコマンドは、サーバー 上の常設チャット データベースから常設チャット データをエクスポートatl-sql-001.contoso.com。エクスポートされたデータは、エクスポートされたファイルにC:\Logs\PersistentChatData.zip。 Level パラメーターが指定されていないので、コマンドは常設チャット情報の完全なエクスポートを実行します。
  
```PowerShell
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a>データベースを復元する

常設チャット データの復元方法は、バックアップに使用した方法によって異なります。 バックアップ手順をSQL Server場合は、復元手順SQL Server使用する必要があります。 **Export-CsPersistentChatData** コマンドレットを使用して常設チャット データをバックアップした場合は **、Import-CsPersistentChatData** コマンドレットを使用してデータを復元する必要があります。
  
```PowerShell
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

または
  
```PowerShell
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
