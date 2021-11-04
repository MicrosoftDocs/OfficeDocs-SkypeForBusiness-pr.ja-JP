---
title: CDR データの保持を指定Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
description: '概要: 通話の詳細記録 (CDR) データを管理する方法についてSkype for Business Server。'
ms.openlocfilehash: ac021da1c2235256e4b9bffc2f8664a1572d27d1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60742133"
---
# <a name="specify-retention-of-cdr-data-in-skype-for-business-server"></a>CDR データの保持を指定Skype for Business Server
 
**概要:** 通話の詳細記録 (CDR) データを管理する方法について説明Skype for Business Server。
  
既定では、通話詳細記録 (CDR) データは 60 日後に削除されます。 [**通話詳細記録**] ページの設定を使用して、このデータを既定よりも長期間、または短期間保持できます。 CDR を無効にすると、CDR を有効にする前に取得されたデータも削除の対象になります。
  
> [!NOTE]
> CDR と QoE (Quality of Experience) を構成して、データが同じ日数保持されるようにする必要があります。 通話詳細記録 (CDR) 内の各通話は、監視サーバー レポートの Web ページから取得できます。これには、CDR 情報と QoE 情報の両方が含まれます。 削除期間が CDR と QoE で異なると、CDR データのみ含む通話がある一方で、QoE データのみ含む通話があることになります。 
  
CDR データの削除設定を構成するには、次の手順を実行します。 
  
### <a name="to-specify-retention-of-cdr-data"></a>CDR データの保持期間を指定するには

1. RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator 役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。  
    
3. 左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**通話詳細記録**] をクリックします。
    
4. [**通話詳細記録**] ページで、表から適切なサイトをクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。
    
5. 削除を有効にするには、[**CDR の削除を有効にする**] を選択します。
    
6. [**CDR を保持する最大期間 (日数)**] で、通話詳細記録を保持する必要のある最大日数を選択します。
    
7. [**エラー報告データの最大保持期間 (日)**] で、 エラー報告を保持する必要のある最大日数を選択します。
    
8. [**確定**] をクリックします。
    
## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a>コマンドレットを使用した CDR 保持Windows PowerShellする

Windows PowerShell と Set-CsCdrConfiguration コマンドレットを使用して、CDR の保持設定を作成できます。 このコマンドレットは、管理者管理シェルSkype for Business Serverリモート セッションから実行Windows PowerShell。 リモート サーバーを使用してサーバー Windows PowerShellする方法[Skype for Business Server、Microsoft Lync リモート PowerShell 管理を参照してください](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/)。 このプロセスは、同じSkype for Business Server。
  
### <a name="to-specify-cdr-retention-for-a-specific-location"></a>特定のロケーションに対して CDR の保持を指定するには

- このコマンドを実行すると、レドモンド サイトでの CDR データの削除が有効になり、CDR データとエラー レポートの両方を 20 日間保持するようにサイトが構成されます。
    
  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

### <a name="to-specify-cdr-retention-for-multiple-locations"></a>複数のロケーションに対して CDR の保持を指定するには

- このコマンドを実行すると、組織内で使用されているすべての CDR 構成設定に対して CDR の保持が構成されます。
    
  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

詳細については [、Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) コマンドレットのヘルプ トピックを参照してください。
  
## <a name="see-also"></a>関連項目

[通話詳細記録 (CDR) Skype for Business Server](call-detail-recording-cdr.md)