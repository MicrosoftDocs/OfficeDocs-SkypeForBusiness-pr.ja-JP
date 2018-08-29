---
title: ビジネス サーバーの Skype の高品質のエクスペリエンスの設定を変更します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
description: 概要では、Skype のビジネス サーバーの QoE データの保存期間を指定する方法について説明します。
ms.openlocfilehash: 743f3df6f58392e7d9107be9ae4c9313ef7a6781
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "23243454"
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server"></a>ビジネス サーバーの Skype の高品質のエクスペリエンスの設定を変更します。

**の概要:** Skype のビジネス サーバーの QoE データの保存期間を指定する方法について説明します。

既定では、QoE (Quality of Experience) データは 60 日後に削除されます。[**QoE データ**] ページの設定を使用して、データの保持期間を延長または短縮できます。QoE を無効にすると、QoE が有効化される前に取得されたデータも削除の対象になります。

> [!NOTE]
> 通話詳細記録 (CDR) と QoE のデータ保持日数は、同じ日数に構成する必要があります。[監視レポート] ホーム ページで入手できる、通話の詳細レポート (CDR) の通話ごとの情報には、CDR と QoE の情報が含まれています。削除間隔が CDR と QoE で異なると、CDR データしかない通話がある一方で、QoE データしかない通話があることになります。

次の手順では、QoE データの削除設定を構成する方法について説明します。

### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a>ビジネス サーバーのコントロール パネルの Skype を使用して、QoE データの保存期間を指定するには

1.  RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator のロールのメンバーとしてコンピューターにログオンします。 詳細については、**セットアップのアクセス許可の委任**を参照してください。

2. 、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。

3. 左側のナビゲーション バーで [**監視とアーカイブ**] をクリックし、[**QoE データ**] をクリックします。

4. [**QoE データ**] ページで、表から該当するサイトをクリックして、[**編集**] をクリックし、[**詳細の表示**] をクリックします。

5. 削除を有効にするには、[**QoE データの削除を有効にする**] を選択します。

6. [**QoE データを保持する最大期間 (日数)**] で、QoE データを保持する必要のある最大日数を選択します。

7. [**コミット**] をクリックします。

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して、QoE の保存期間を指定します。

QoE の保存期間の設定は、Windows PowerShell と**セット CsQoEConfiguration**コマンドレットを使用して作成できます。 実行できますこのコマンドレットのいずれか、Skype からビジネス サーバー管理シェルまたは Windows PowerShell のリモート セッションから。 ビジネス サーバーの Skype に接続するリモートの Windows PowerShell を使用する詳細については、ブログ記事の[「クイック スタート:: を管理する Microsoft Lync サーバー 2010 を使用してリモート PowerShell」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。 プロセスは、Skype のビジネス サーバーで同じです。

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

詳細については、[セット CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps)コマンドレットのヘルプ トピックを参照してください。

## <a name="see-also"></a>関連項目

[監視を展開します。](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)