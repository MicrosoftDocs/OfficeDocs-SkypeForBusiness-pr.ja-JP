---
title: Skype for Business Server でのエクスペリエンスの品質設定の変更
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
ms.openlocfilehash: cba8b2b98aa809c0583ad7323ff846e654ca9ace
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118616"
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server"></a>Skype for Business Server でのエクスペリエンスの品質設定の変更

**概要:** Skype for Business Server で QoE データの保持を指定する方法について学習します。

既定では、QoE (Quality of Experience) データは 60 日後に削除されます。 [**QoE データ**] ページの設定を使用して、データの保持期間を延長または短縮できます。 QoE を無効にすると、QoE が有効化される前に取得されたデータも削除の対象になります。

> [!NOTE]
> 通話詳細記録 (CDR) と QoE のデータ保持日数は、同じ日数に構成する必要があります。[監視レポート] ホーム ページで入手できる、通話の詳細レポート (CDR) の通話ごとの情報には、CDR と QoE の情報が含まれています。削除間隔が CDR と QoE で異なると、CDR データしかない通話がある一方で、QoE データしかない通話があることになります。

次の手順では、QoE データの削除設定を構成する方法について説明します。

### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルを使用して QoE データの保持を指定するには

1.  RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「**セットアップのアクセス許可の委任**」を参照してください。

2. ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。

3. 左側のナビゲーション バーで [**監視とアーカイブ**] をクリックし、[**QoE データ**] をクリックします。

4. [**QoE データ**] ページで、表から該当するサイトをクリックして、[**編集**] をクリックし、[**詳細の表示**] をクリックします。

5. 削除を有効にするには、[**QoE データの削除を有効にする**] を選択します。

6. [**QoE データを保持する最大期間 (日数)**] で、QoE データを保持する必要のある最大日数を選択します。

7. [**確定**] をクリックします。

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a>コマンドレットを使用した QoE 保持Windows PowerShellする

QoE 保持設定を作成するには、Windows PowerShell **Set-CsQoEConfiguration コマンドレットを使用** します。 このコマンドレットは、Skype for Business Server 管理シェルから、またはサーバーのリモート セッションから実行Windows PowerShell。 リモート Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「クイック スタート: リモート PowerShell を使用した [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)の管理」を参照してください。 このプロセスは、Skype for Business Server でも同じです。

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