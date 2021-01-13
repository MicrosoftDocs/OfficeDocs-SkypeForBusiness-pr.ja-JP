---
title: Skype for Business Server でアーカイブされたデータの削除を管理する
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
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: '概要: Skype for Business Server のアーカイブ データの削除を管理する方法について学習します。'
ms.openlocfilehash: aecc78f84b3cd4b745a96e534535c98c1739c156
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828537"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a>Skype for Business Server でアーカイブされたデータの削除を管理する

**概要:** Skype for Business Server のアーカイブ データの削除を管理する方法について学習します。
  
アーカイブ データベースは長期保持を目的としていないので、Skype for Business Server はアーカイブされたデータの電子検出 (検索) ソリューションを提供していないので、データを他のストレージに移動する必要があります。 Skype for Business Server は、アーカイブされたデータを検索可能なトランスクリプトにエクスポートするために使用できるセッション エクスポート ツールを提供します。 アーカイブおよびエクスポートされたデータを削除する場合を定義する必要があります。 
  
**Export-CsArchivingData** コマンドレットを使用したデータのエクスポートの詳細については [、「Skype for Business Server](export-archived-data.md)でアーカイブされたデータをエクスポートする」を参照してください。
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a>コントロール パネルを使用してデータの削除を管理する

コントロール パネルを使用してアーカイブされたデータの削除を管理するには:
  
1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 
    
2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。 
    
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
    
たとえば、次のコマンドを実行すると、アーカイブ済みのすべてのデータを削除できます。 このコマンドを実行すると、Skype for Business Server は KeepArchivingDataForDays パラメーターに指定された値より古いアーカイブ レコードをすべて削除します。 
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

次のコマンドは **、(Export-CSArchivingData** コマンドレットを使用して) データ ファイルにエクスポートされたアーカイブ済みレコードに削除を制限します。 PurgeExportedArchivesOnly パラメーターを True ($True) に設定する必要があります。
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

このコマンドを実行すると、Skype for Business Server は 2 つの条件 (1) KeepArchivingDataForDays パラメーターに指定された値より古いアーカイブ レコードのみを削除します。2) **Export-CsArchivingData** コマンドレットを使用してエクスポートされています。
  
アーカイブ レコードの自動削除を無効にするには、EnablePurging パラメーターを False ($False) に設定します。
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

次の例では **、Invoke-CsArchivingDatabasePurge** コマンドレットを使用して、データベース上のアーカイブ データベースから 24 時間以上前のすべてのレコードを削除atl-sql-001.contoso.com。 エクスポートされていないレコードも含め、すべてのレコードが確実に削除されるには、PurgeExportedArchivesOnly パラメーターを False ($False) に設定します。
  
```PowerShell
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
