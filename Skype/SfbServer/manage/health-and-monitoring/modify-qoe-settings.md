---
title: '[エクスペリエンスの品質] 設定を変更Skype for Business Server'
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
description: '概要: QoE データの保持を指定する方法については、Skype for Business Server。'
ms.openlocfilehash: 7960f7c89ce16a7105cf24cc89d5efd660fe260b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60855524"
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server"></a>[エクスペリエンスの品質] 設定を変更Skype for Business Server

**概要:** QoE データの保持を指定する方法については、Skype for Business Server。

既定では、QoE (Quality of Experience) データは 60 日後に削除されます。 [**QoE データ**] ページの設定を使用して、データの保持期間を延長または短縮できます。 QoE を無効にすると、QoE が有効化される前に取得されたデータも削除の対象になります。

> [!NOTE]
> 通話詳細記録 (CDR) と QoE のデータ保持日数は、同じ日数に構成する必要があります。[監視レポート] ホーム ページで入手できる、通話の詳細レポート (CDR) の通話ごとの情報には、CDR と QoE の情報が含まれています。削除間隔が CDR と QoE で異なると、CDR データしかない通話がある一方で、QoE データしかない通話があることになります。

次の手順では、QoE データの削除設定を構成する方法について説明します。

### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a>コントロール パネルを使用して QoE データの保持をSkype for Business Serverするには

1.  RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「**セットアップのアクセス許可の委任**」を参照してください。

2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。

3. 左側のナビゲーション バーで [**監視とアーカイブ**] をクリックし、[**QoE データ**] をクリックします。

4. [**QoE データ**] ページで、表から該当するサイトをクリックして、[**編集**] をクリックし、[**詳細の表示**] をクリックします。

5. 削除を有効にするには、[**QoE データの削除を有効にする**] を選択します。

6. [**QoE データを保持する最大期間 (日数)**] で、QoE データを保持する必要のある最大日数を選択します。

7. [**確定**] をクリックします。

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a>コマンドレットを使用した QoE 保持Windows PowerShellする

QoE 保持設定を作成するには、Windows PowerShell **Set-CsQoEConfiguration コマンドレットを使用** します。 このコマンドレットは、管理者管理シェルSkype for Business Serverリモート セッションから実行Windows PowerShell。 リモート サーバーを使用してサーバー Windows PowerShellする方法[Skype for Business Server、Microsoft Lync リモート PowerShell 管理を参照してください](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/)。 このプロセスは、同じSkype for Business Server。

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

詳細については [、Set-CsQoEConfiguration](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps) コマンドレットのヘルプ トピックを参照してください。

## <a name="see-also"></a>関連項目

[監視の展開](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)