---
title: ビジネス サーバーの Skype でのアーカイブ ・ データの削除を管理します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: '概要: は、Skype のビジネス サーバーのアーカイブ ・ データのパージを管理する方法を説明します。'
ms.openlocfilehash: fce7c8214eddd55736a54b960d57053a88cdc859
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20997945"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a>ビジネス サーバーの Skype でのアーカイブ ・ データの削除を管理します。

**の概要:** ビジネス サーバー用の Skype のアーカイブ ・ データのパージを管理する方法について説明します。
  
アーカイブ データベースは、長期的な保存は、ありませんし、Skype のビジネス サーバー ソリューションが提供されない、(検索) を電子的証拠開示アーカイブ ・ データは、データを他のストレージに移動する必要があるため。 ビジネス サーバー用の Skype は、アーカイブ ・ データを検索可能なトラン スクリプトにエクスポートするのには使用できるセッション エクスポート ツールを提供します。 アーカイブされたデータやエクスポートされたデータをいつ削除するかを定義する必要があります。 
  
**.Eml という**コマンドレットを使用してデータをエクスポートする方法の詳細については、 [Skype のビジネス サーバーでアーカイブされたデータをエクスポートする](export-archived-data.md)を参照してください。
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a>コントロール パネルを使用してデータの削除を管理する

コントロール パネルを使用してデータの削除を管理するには、次の操作を行います。
  
1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 
    
2. 、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 
    
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
    
たとえば、次のコマンドを使用するとアーカイブされている全データの削除を有効にできます。 このコマンドを実行すると、Skype のビジネス サーバーは KeepArchivingDataForDays パラメーターに指定された値より古いすべてのアーカイブのレコードをパージします。 
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

次のコマンドは、( **.eml という**コマンドレットを使用して) でのデータ ファイルにエクスポートされたアーカイブされた記録の削除を制限します。 True ($True) に、PurgeExportedArchivesOnly パラメーターを設定することもあります。
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

このコマンドを実行すると、Skype ビジネス サーバーの 2 つの条件を満たすレコードをアーカイブにのみパージされます: 1) KeepArchivingDataForDays パラメーターに指定した値よりも古い2) **.eml という**コマンドレットを使用してエクスポートされました。
  
アーカイブ レコードの自動削除を無効にするには、EnablePurging パラメーターを False ($False) に設定します。
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

次の例では、atl の sql-001.contoso.com のアーカイブ データベースから 24 時間を超えるすべてのレコードを削除するのに**呼び出し CsArchivingDatabasePurge**コマンドレットを使用します。 該当するレコードが、エクスポートされていないレコードも含めてすべて確実に削除されるようにするために、PurgeExportedArchivesOnly パラメーターを False ($False) に設定しています。
  
```
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```