---
title: Skype for Business Server で Quality of Experience の設定を変更する
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
ms.assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
description: '概要: Skype for Business Server で QoE データの保持を指定する方法について学習します。'
ms.openlocfilehash: 18776e9b8eec9dcff6ced9f654d8153d7fa01777
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827797"
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server"></a>Skype for Business Server で Quality of Experience の設定を変更する

**概要:** Skype for Business Server で QoE データの保持を指定する方法について学習します。

既定では、QoE (Quality of Experience) データは 60 日後に削除されます。 [**QoE データ**] ページの設定を使用して、データの保持期間を延長または短縮できます。 QoE を無効にすると、QoE が有効化される前に取得されたデータも削除の対象になります。

> [!NOTE]
> 通話詳細記録 (CDR) と QoE のデータ保持日数は、同じ日数に構成する必要があります。[監視レポート] ホーム ページで入手できる、通話の詳細レポート (CDR) の通話ごとの情報には、CDR と QoE の情報が含まれています。削除間隔が CDR と QoE で異なると、CDR データしかない通話がある一方で、QoE データしかない通話があることになります。

次の手順では、QoE データの削除設定を構成する方法について説明します。

### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルを使用して QoE データの保持を指定するには

1.  RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「**セットアップのアクセス許可の委任**」を参照してください。

2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。

3. 左側のナビゲーション バーで [**監視とアーカイブ**] をクリックし、[**QoE データ**] をクリックします。

4. [**QoE データ**] ページで、表から該当するサイトをクリックして、[**編集**] をクリックし、[**詳細の表示**] をクリックします。

5. 削除を有効にするには、[**QoE データの削除を有効にする**] を選択します。

6. [**QoE データを保持する最大期間 (日数)**] で、QoE データを保持する必要のある最大日数を選択します。

7. [**確定**] をクリックします。

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a>サービス コマンドレットを使用して QoE Windows PowerShellを指定する

QoE 保持設定を作成するには、Windows PowerShell **Set-CsQoEConfiguration コマンドレットを使用** します。 このコマンドレットは、Skype for Business Server 管理シェルまたは Skype for Business Server のリモート セッションから実行Windows PowerShell。 リモート Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「クイック スタート: リモート PowerShell を使用した [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)の管理」を参照してください。 プロセスは Skype for Business Server でも同じです。

### <a name="to-specify-qoe-retention-for-a-specific-location"></a>特定のロケーションに対して QoE の保持を指定するには

- このコマンドを実行すると、レドモンド サイトでの QoE データの削除が有効になり、QoE データを 20 日間保持するようにサイトが構成されます。

  ```PowerShell
  Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20
  ```

### <a name="to-specify-qoe-retention-for-multiple-locations"></a>複数のロケーションに対して QoE の保持を指定するには

- このコマンドを実行すると、組織で使用されているすべての QoE 構成設定で QoE の保持が構成されます。

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20
  ```

詳細については [、Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps) コマンドレットのヘルプ トピックを参照してください。

## <a name="see-also"></a>関連項目

[監視の展開](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
