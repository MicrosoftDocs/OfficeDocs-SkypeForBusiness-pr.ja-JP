---
title: ビジネス サーバー用の Skype での CDR のデータ保存期間を指定します。
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
description: 概要では、Skype のビジネス サーバー (CDR) データを記録する呼び出しの詳細を管理する方法について説明します。
ms.openlocfilehash: 72fbb679a260462086930fc0457b5c748447cc29
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878746"
---
# <a name="specify-retention-of-cdr-data-in-skype-for-business-server"></a>ビジネス サーバー用の Skype での CDR のデータ保存期間を指定します。
 
**の概要:** Skype のビジネス サーバー (CDR) データを記録する呼び出しの詳細を管理する方法について説明します。
  
既定では、通話詳細記録 (CDR) データは 60 日後に削除されます。 [**通話詳細記録**] ページの設定を使用して、このデータを既定よりも長期間、または短期間保持できます。 CDR を無効にすると、CDR を有効にする前に取得されたデータも削除の対象になります。
  
> [!NOTE]
> CDR と QoE (Quality of Experience) を構成して、データが同じ日数保持されるようにする必要があります。通話詳細記録 (CDR) 内の各通話は、監視サーバー レポートの Web ページから取得できます。これには、CDR 情報と QoE 情報の両方が含まれます。削除期間が CDR と QoE で異なると、CDR データのみ含む通話がある一方で、QoE データのみ含む通話があることになります。 
  
CDR データの削除設定を構成するには、次の手順を実行します。 
  
### <a name="to-specify-retention-of-cdr-data"></a>CDR データの保持期間を指定するには

1. RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ)、ユーザー アカウントのロールに割り当てられた、CsServerAdministrator または CsAdministrator、ビジネス サーバーの Skype を導入してネットワーク内の任意のコンピューターにログオンまたは.
    
2. 、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。  
    
3. 左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**通話詳細記録**] をクリックします。
    
4. [**通話詳細記録**] ページで、表から適切なサイトをクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。
    
5. 削除を有効にするには、[**CDR の削除を有効にする**] を選択します。
    
6. [**CDR を保持する最大期間 (日数)**] で、通話詳細記録を保持する必要のある最大日数を選択します。
    
7. [**エラー報告データの最大保持期間 (日)**] で、 エラー報告を保持する必要のある最大日数を選択します。
    
8. [**確定**] をクリックします。
    
## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して、CDR の保存期間を指定します。

CDR 保存期間の設定は、Windows PowerShell とセット CsCdrConfiguration コマンドレットを使用して作成できます。 実行できますこのコマンドレットのいずれか、Skype からビジネス サーバー管理シェルまたは Windows PowerShell のリモート セッションから。 ビジネス サーバーの Skype に接続するリモートの Windows PowerShell を使用する詳細については、ブログ記事の[「クイック スタート:: を管理する Microsoft Lync サーバー 2010 を使用してリモート PowerShell」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。 プロセスは、Skype のビジネス サーバーで同じです。
  
### <a name="to-specify-cdr-retention-for-a-specific-location"></a>特定の場所の CDR の保持期間を指定するには

- このコマンドを実行すると、レドモンド サイトでの CDR データの削除が有効になり、CDR データとエラー レポートの両方を 20 日間保持するようにサイトが構成されます。
    
  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

### <a name="to-specify-cdr-retention-for-multiple-locations"></a>複数の場所の CDR の保持期間を指定するには

- このコマンドを実行すると、組織内で使用されているすべての CDR 構成設定に対して CDR の保持期間が構成されます。
    
  ```
  Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

詳細については、[セット CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)コマンドレットのヘルプ トピックを参照してください。
  
## <a name="see-also"></a>関連項目

[Skype のビジネス サーバー (CDR) を記録する詳細を呼び出す](call-detail-recording-cdr.md)
