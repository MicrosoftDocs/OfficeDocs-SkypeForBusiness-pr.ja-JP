---
title: アーカイブされたデータの削除を管理Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: '概要: アーカイブされたデータの削除を管理する方法についてSkype for Business Server。'
ms.openlocfilehash: 9868277bc79a95b869383025da7e1c52aed35921
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62395379"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a>アーカイブされたデータの削除を管理Skype for Business Server

**概要:** アーカイブされたデータの削除を管理する方法についてSkype for Business Server。
  
アーカイブ データベースは長期的な保持を目的としていないので、Skype for Business Server はアーカイブ されたデータに対する電子探索 (検索) ソリューションを提供しないので、データを他のストレージに移動する必要があります。 Skype for Business Serverは、アーカイブされたデータを検索可能なトランスクリプトにエクスポートするために使用できるセッション エクスポート ツールを提供します。 アーカイブおよびエクスポートされたデータを削除する場合を定義する必要があります。 
  
**Export-CsArchivingData** コマンドレットを使用したデータのエクスポートの詳細については、「Export [archived data in Skype for Business Server」 を参照してください](export-archived-data.md)。
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a>コントロール パネルを使用してデータの削除を管理する

コントロール パネルを使用してアーカイブされたデータの削除を管理するには、次の操作を行います。
  
1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。 
    
3. 左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。
    
4. アーカイブ構成の一覧で、適切なグローバル、サイト、またはプール構成の名前をクリックし、[**編集**]、[**詳細の表示**] の順にクリックします。その後、次の操作を行います。
    
   - 削除を有効にする場合は、[**アーカイブ データの削除を有効にする**] チェック ボックスをオンにして、次のいずれかの操作を行います。
    
     - すべてのレコードを削除する場合は、[**最大日数が経過したエクスポートおよび保存済みアーカイブ データを削除する**] をクリックして、日数を指定します。
    
     - エクスポートされたデータのみを削除する場合は、[**エクスポート済みのアーカイブ データのみを削除する**] をクリックします。
    
   - 削除を無効にするには、[**アーカイブ データの削除を有効にする**] チェック ボックスをオフにします。
    
5. [**確定**] をクリックします。
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a>データを使用してデータの削除を管理Windows PowerShell

次のコマンドレットを使用して、アーカイブされたデータの削除Windows PowerShellできます。
  
- **EnablePurging パラメーターを指定した Set-CsArchivingConfiguration** コマンドレットを使用すると、アーカイブされたデータの削除を有効または無効にできます。
    
- **Invoke-CsArchivingDatabasePurge** を使用すると、アーカイブ データベースからレコードを手動で削除できます。
    
たとえば、次のコマンドを使用すると、すべてのアーカイブ データを削除できます。 このコマンドを実行するとSkype for Business Server KeepArchivingDataForDays パラメーターに指定された値より古いアーカイブ レコードはすべて削除されます。 
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

次のコマンドは、( **Export-CSArchivingData** コマンドレットを使用して) データ ファイルにエクスポートされたアーカイブ されたレコードへの削除を制限します。 PurgeExportedArchivesOnly パラメーターを True ($True) に設定する必要があります。
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

このコマンドを実行すると、Skype for Business Server は 2 つの条件を満たすアーカイブ レコードのみを削除します。1) KeepArchivingDataForDays パラメーターに指定された値より古い値です。2) **Export-CsArchivingData** コマンドレットを使用してエクスポートされています。
  
アーカイブ レコードの自動削除を無効にするには、EnablePurging パラメーターを False ($False) に設定します。
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

次の例では **、Invoke-CsArchivingDatabasePurge** コマンドレットを使用して、24 時間以上前のすべてのレコードを、atl-sql-001.contoso.com のアーカイブ データベースから削除します。 エクスポートされていないレコードを含むすべてのレコードが削除される場合、PurgeExportedArchivesOnly パラメーターは False ($False) に設定されます。
  
```PowerShell
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
