---
title: Skype for Business Server 2015 での常設チャット データベースのバックアップと復元
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: '概要: は、バックアップおよびビジネス サーバー 2015 の Skype での永続的なチャット サーバーのデータベースを復元する方法を説明します。'
ms.openlocfilehash: ae4f0241195eca115e5a579d55a34025e6c9da5c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910362"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での常設チャット データベースのバックアップと復元
 
**の概要:** バックアップおよびビジネス サーバー 2015 の Skype での永続的なチャット サーバーのデータベースを復元する方法について説明します。
  
永続的なチャット サーバーには、履歴とコンテンツ、構成、ユーザー プロビジョニング、およびその他の関連するメタデータなど、チャット ルームのデータを格納する SQL Server データベースのソフトウェアが必要です。 さらに、組織にアーカイブするには、永続的なチャットの活動を必要とする規制があり、オプションのコンプライアンス サービスが有効になっている場合は、SQL Server データベース ソフトウェアを使用して内容を含めチャット イベントでは、次のように、コンプライアンス データを格納参加と、部屋のままです。 チャット ルームの内容は、永続的なチャット (mgc) データベースに格納されます。 コンプライアンス データはコンプライアンス データベース (mgccomp) に保管されます。 コンプライアンス データは非常に重要なビジネス データであり、定期的なバックアップが必要です。 
  
> [!NOTE]
> 永続的なチャットですがビジネス サーバー 2015 の Skype で利用可能なビジネス サーバー 2019 の Skype でサポートされていません。 同じ機能は、チームで使用できます。 詳細については、[マイクロソフトのチームにビジネス用の Skype からの旅](/microsoftteams/journey-skypeforbusiness-teams)を参照してください。 永続的なチャットを使用する場合は、選択肢は、いずれかをチームでは、この機能を必要とするユーザーを移行するまたはビジネス サーバー 2015 の Skype を使用し続ける。 

## <a name="back-up-the-databases"></a>データベースをバックアップする

永続的なチャットのデータのバックアップの 2 つの方法もあります。 
  
- SQL Server バックアップ
    
- 永続的なチャットのデータをファイルとしてエクスポートする**エクスポート CsPersistentChatData**コマンドレットは、
    
SQL Server バックアップを使用して作成されるデータには、**Export-CsPersistentChatData** で作成する場合に比べて、非常に多くのディスク容量 (場合によっては 20 倍) が必要ですが、SQL Server バックアップは管理者がよく利用する方法です。
  
SQL Server バックアップ手順を使用する場合は、詳細について SQL のマニュアルを参照してください。 
  
**Export-CsPersistentChatData** コマンドレットを使用する場合は、コマンドを次のように指定します。
  
```
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

または
  
```
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

たとえば、次に示すコマンドは、常設チャット データをサーバー atl-sql-001.contoso.com 上の常設チャット データベースからエクスポートします。エクスポートされたデータは、ファイル C:\Logs\PersistentChatData.zip に格納されます。Level パラメーターが指定されていないので、このコマンドは常設チャットの情報をすべてエクスポートします。
  
```
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a>データベースを復元する

永続的なチャット データを復元する方法は、バックアップを作成するために使用する方法によって異なります。 SQL Server バックアップ手順を使用した場合は、SQL Server 復元手順を使用する必要があります。 永続的なチャットのデータをバックアップするには、**エクスポート CsPersistentChatData**コマンドレットを使用する場合は、データを復元するのには**インポート CsPersistentChatData**コマンドレットを使用する必要があります。
  
```
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

または
  
```
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
