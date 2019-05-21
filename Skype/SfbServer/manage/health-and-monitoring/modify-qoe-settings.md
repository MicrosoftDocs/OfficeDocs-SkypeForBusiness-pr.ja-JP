---
title: Skype for Business Server でエクスペリエンス設定の品質を変更する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
description: '概要: Skype for Business Server で QoE データの保持を指定する方法について説明します。'
ms.openlocfilehash: 89e20b18aa285bd4ee61df12c822e487dd6b37a4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280006"
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server"></a>Skype for Business Server でエクスペリエンス設定の品質を変更する

**概要:** Skype for Business Server で QoE データの保持を指定する方法について説明します。

既定では、QoE (Quality of Experience) データは 60 日後に削除されます。[**QoE データ**] ページの設定を使用して、データの保持期間を延長または短縮できます。QoE を無効にすると、QoE が有効化される前に取得されたデータも削除の対象になります。

> [!NOTE]
> 通話詳細記録 (CDR) と QoE のデータ保持日数は、同じ日数に構成する必要があります。[監視レポート] ホーム ページで入手できる、通話の詳細レポート (CDR) の通話ごとの情報には、CDR と QoE の情報が含まれています。削除間隔が CDR と QoE で異なると、CDR データしかない通話がある一方で、QoE データしかない通話があることになります。

次の手順では、QoE データの削除設定を構成する方法について説明します。

### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルを使用して QoE データの保持を指定するには

1.  RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「**Delegate Setup Permissions**」を参照してください。

2. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。

3. 左側のナビゲーション バーで [**監視とアーカイブ**] をクリックし、[**QoE データ**] をクリックします。

4. [**QoE データ**] ページで、表から該当するサイトをクリックして、[**編集**] をクリックし、[**詳細の表示**] をクリックします。

5. 削除を有効にするには、[**QoE データの削除を有効にする**] を選択します。

6. [**QoE データを保持する最大期間 (日数)**] で、QoE データを保持する必要のある最大日数を選択します。

7. [**コミット**] をクリックします。

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用した QoE 保持の指定

QoE 保持設定を作成するには、Windows PowerShell と**Set-CsQoEConfiguration**コマンドレットを使用します。 このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションからでも実行できます。 リモートの Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「[クイックスタート: リモート PowerShell を使用した Microsoft Lync server 2010 の管理」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。 このプロセスは、Skype for Business Server でも同じです。

### <a name="to-specify-qoe-retention-for-a-specific-location"></a>特定の場所で QoE の保持を指定するには

- このコマンドを実行すると、レドモンド サイトでの QoE データの削除が有効になり、QoE データを 20 日間保持するようにサイトが構成されます。

  ```
  Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20
  ```

### <a name="to-specify-qoe-retention-for-multiple-locations"></a>複数の場所で QoE の保持を指定するには

- このコマンドを実行すると、組織で使用されているすべての QoE 構成設定で QoE の保持が構成されます。

  ```
  Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20
  ```

詳細については、「 [Set-CsQoEConfiguration 設定](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps)」コマンドレットのヘルプトピックを参照してください。

## <a name="see-also"></a>関連項目

[Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
