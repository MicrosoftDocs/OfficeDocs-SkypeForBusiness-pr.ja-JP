---
title: Skype for Business Server でアーカイブデータの削除を管理する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: '概要: Skype for Business Server のアーカイブデータの削除を管理する方法について説明します。'
ms.openlocfilehash: 193e17791290b384552542129d8d89c20296f109
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278392"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a>Skype for Business Server でアーカイブデータの削除を管理する

**概要:** Skype for Business Server のアーカイブデータの削除を管理する方法について説明します。
  
アーカイブデータベースは、長期間の保存のためのものではありません。また、Skype for Business Server では、アーカイブデータの電子的な探索 (検索) ソリューションを提供していないため、データを他のストレージに移動する必要があります。 Skype for Business Server には、アーカイブデータを検索可能なトランスクリプトにエクスポートするために使用できるセッションエクスポートツールが用意されています。 アーカイブされたデータやエクスポートされたデータをいつ削除するかを定義する必要があります。 
  
**CsArchivingData**コマンドレットを使用してデータをエクスポートする方法について詳しくは、「 [Skype for business Server にアーカイブデータをエクスポート](export-archived-data.md)する」をご覧ください。
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a>コントロール パネルを使用してデータの削除を管理する

コントロール パネルを使用してデータの削除を管理するには、次の操作を行います。
  
1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 
    
2. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 
    
3. 左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。
    
4. アーカイブ構成の一覧から、適切なグローバル構成、サイト構成、またはプール構成の名前をクリックし、[**編集**]、[**詳細の表示**] の順にクリックし、次の操作を実行します。
    
   - 削除を有効にする場合は、[**アーカイブ データの削除を有効にする**] チェック ボックスをオンにし、次のいずれかの操作を行います。
    
     - すべてのレコードを削除する場合は、[**最大日数が経過したエクスポートおよび保存済みアーカイブ データを削除する**] をクリックし、日数を指定します。
    
     - エクスポートされたデータのみを削除する場合は、[**エクスポート済みのアーカイブ データのみを削除する**] をクリックします。
    
   - 削除を無効にするには、[**アーカイブ データの削除を有効にする**] チェック ボックスをオフにします。
    
5. [**確定**] をクリックします。
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a>Windows PowerShell を使用したデータの削除を管理する

アーカイブされたデータの削除は、次の Windows PowerShell コマンドレットを使用して管理できます。
  
- **Set-CsArchivingConfiguration** コマンドレットで EnablePurging パラメーターを指定すると、アーカイブされたデータの削除を有効または無効にできます。
    
- **Invoke-CsArchivingDatabasePurge** を使用すると、アーカイブ データベースからレコードを手動で削除できます。
    
たとえば、次のコマンドを使用するとアーカイブされている全データの削除を有効にできます。 このコマンドを実行すると、Skype for Business Server は、KeepArchivingDataForDays パラメーターに指定された値よりも古いすべてのアーカイブレコードを削除します。 
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

次のコマンドは、データファイルにエクスポートされた ( **CSArchivingData**コマンドレットを使用して) アーカイブされたレコードの削除を制限します。 PurgeExportedArchivesOnly パラメーターを True ($True) に設定する必要もあります。
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

このコマンドを実行すると、Skype for Business Server は、2つの条件を満たすレコードのみを消去します。 1) は、KeepArchivingDataForDays パラメーターに指定された値よりも古いものです。and、2) **CsArchivingData**コマンドレットを使用してエクスポートされている。
  
アーカイブ レコードの自動削除を無効にするには、EnablePurging パラメーターを False ($False) に設定します。
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

次の例では、 **CsArchivingDatabasePurge**コマンドレットを使用して、atl-sql-001.contoso.com のアーカイブデータベースから24時間以上経過したレコードをすべて削除します。 該当するレコードが、エクスポートされていないレコードも含めてすべて確実に削除されるようにするために、PurgeExportedArchivesOnly パラメーターを False ($False) に設定しています。
  
```
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
