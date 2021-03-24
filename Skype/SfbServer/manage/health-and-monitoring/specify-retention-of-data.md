---
title: Skype for Business Server での CDR データの保持の指定
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
ms.assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
description: '概要: Skype for Business Server の通話詳細記録 (CDR) データを管理する方法について説明します。'
ms.openlocfilehash: abf6461a76ced9d3ba07e4c5157dd4d14bab60a3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104393"
---
# <a name="specify-retention-of-cdr-data-in-skype-for-business-server"></a>Skype for Business Server での CDR データの保持の指定
 
**概要:** Skype for Business Server の通話詳細記録 (CDR) データを管理する方法について説明します。
  
既定では、通話詳細記録 (CDR) データは 60 日後に削除されます。 [**通話詳細記録**] ページの設定を使用して、このデータを既定よりも長期間、または短期間保持できます。 CDR を無効にすると、CDR を有効にする前に取得されたデータも削除の対象になります。
  
> [!NOTE]
> CDR と QoE (Quality of Experience) を構成して、データが同じ日数保持されるようにする必要があります。 通話詳細記録 (CDR) 内の各通話は、監視サーバー レポートの Web ページから取得できます。これには、CDR 情報と QoE 情報の両方が含まれます。 削除期間が CDR と QoE で異なると、CDR データのみ含む通話がある一方で、QoE データのみ含む通話があることになります。 
  
CDR データの削除設定を構成するには、次の手順を実行します。 
  
### <a name="to-specify-retention-of-cdr-data"></a>CDR データの保持期間を指定するには

1. RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator 役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。  
    
3. 左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**通話詳細記録**] をクリックします。
    
4. [**通話詳細記録**] ページで、表から適切なサイトをクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。
    
5. 削除を有効にするには、[**CDR の削除を有効にする**] を選択します。
    
6. [**CDR を保持する最大期間 (日数)**] で、通話詳細記録を保持する必要のある最大日数を選択します。
    
7. [**エラー報告データの最大保持期間 (日)**] で、 エラー報告を保持する必要のある最大日数を選択します。
    
8. [**確定**] をクリックします。
    
## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a>コマンドレットを使用した CDR 保持Windows PowerShellする

Windows PowerShell と Set-CsCdrConfiguration コマンドレットを使用して、CDR の保持設定を作成できます。 このコマンドレットは、Skype for Business Server 管理シェルから、またはサーバーのリモート セッションから実行Windows PowerShell。 リモート Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「クイック スタート: リモート PowerShell を使用した [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)の管理」を参照してください。 このプロセスは、Skype for Business Server でも同じです。
  
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

[Skype for Business Server での通話詳細記録 (CDR)](call-detail-recording-cdr.md)