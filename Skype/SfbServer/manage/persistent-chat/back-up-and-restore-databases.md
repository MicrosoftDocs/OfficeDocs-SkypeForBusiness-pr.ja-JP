---
title: Skype for Business Server 2015 での常設チャット データベースのバックアップと復元
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: '概要: Skype for Business Server 2015 で永続的なチャットサーバーデータベースのバックアップと復元を行う方法について説明します。'
ms.openlocfilehash: 9da64a3ba6f6ad8053faebf0d536a610e02cce8f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817343"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での常設チャット データベースのバックアップと復元
 
**概要:** Skype for Business Server 2015 で永続的なチャットサーバーデータベースのバックアップと復元を行う方法について説明します。
  
常設チャットサーバーには、履歴とコンテンツ、構成、ユーザーのプロビジョニングなど、関連するメタデータを保存するための SQL Server データベースソフトウェアが必要です。 また、アーカイブするための常設チャット活動を必要とする規制が組織にあり、オプションのコンプライアンスサービスが有効になっている場合、SQL Server データベースソフトウェアを使用して、チャットのコンテンツやイベントなどのコンプライアンスデータを保存することができます。会議室からの参加と退室。 チャットルームのコンテンツは、常設チャットデータベース (行う) に保存されます。 コンプライアンス データはコンプライアンス データベース (mgccomp) に保管されます。 コンプライアンス データは非常に重要なビジネス データであり、定期的なバックアップが必要です。 
  
> [!NOTE]
> 常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 Teams でも同じ機能を使用できます。 詳細については、「 [Microsoft Teams のアップグレードの](/microsoftteams/upgrade-start-here)概要」を参照してください。 常設チャットを使用する必要がある場合は、この機能が必要なユーザーをチームに移行するか、Skype for Business Server 2015 を使い続けるかのいずれかを選択できます。 

## <a name="back-up-the-databases"></a>データベースをバックアップする

常設チャットデータをバックアップするには、2つの方法があります。 
  
- SQL Server バックアップ
    
- **CsPersistentChatData**コマンドレット。常設のチャットデータをファイルとしてエクスポートします。
    
SQL Server バックアップを使用して作成されるデータには、**Export-CsPersistentChatData** で作成する場合に比べて、非常に多くのディスク容量 (場合によっては 20 倍) が必要ですが、SQL Server バックアップは管理者がよく利用する方法です。
  
SQL Server バックアップ手順を使用する場合は、詳細について SQL のマニュアルを参照してください。 
  
**Export-CsPersistentChatData** コマンドレットを使用する場合は、コマンドを次のように指定します。
  
```PowerShell
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

または
  
```PowerShell
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

たとえば、次に示すコマンドは、常設チャット データをサーバー atl-sql-001.contoso.com 上の常設チャット データベースからエクスポートします。エクスポートされたデータは、ファイル C:\Logs\PersistentChatData.zip に格納されます。Level パラメーターが指定されていないので、このコマンドは常設チャットの情報をすべてエクスポートします。
  
```PowerShell
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a>データベースを復元する

常設チャットのデータを復元する方法は、バックアップに使用した方法によって異なります。 SQL Server バックアップ手順を使用した場合は、SQL Server 復元手順を使用する必要があります。 **CsPersistentChatData**コマンドレットを使用して常設チャットデータをバックアップする場合は、 **CsPersistentChatData**コマンドレットを使用してデータを復元する必要があります。
  
```PowerShell
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

または
  
```PowerShell
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
