---
title: QoE (Quality of Experience) 設定の変更
TOCTitle: QoE (Quality of Experience) 設定の変更
ms:assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg182563(v=OCS.15)
ms:contentKeyID: 48273194
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# QoE (Quality of Experience) 設定の変更

 

_**トピックの最終更新日:** 2013-02-23_

既定では、QoE (Quality of Experience) データは 60 日後に削除されます。 \[**QoE データ**\] ページの設定を使用して、データの保持期間を延長または短縮できます。 QoE を無効にすると、QoE が有効化される前に取得されたデータも削除の対象になります。

> [!NOTE]
> 通話詳細記録 (CDR) と QoE のデータ保持日数は、同じ日数に構成する必要があります。[監視レポート] ホーム ページで入手できる、通話の詳細レポート (CDR) の通話ごとの情報には、CDR と QoE の情報が含まれています。削除間隔が CDR と QoE で異なると、CDR データしかない通話がある一方で、QoE データしかない通話があることになります。


次の手順では、QoE データの削除設定を構成する方法について説明します。

## Lync Server コントロール パネルを使用して QoE データの保持を指定するには

1.  RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「[Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**監視とアーカイブ**\] をクリックし、\[**QoE データ**\] をクリックします。

4.  \[**QoE データ**\] ページで、表から該当するサイトをクリックして、\[**編集**\] をクリックし、\[**詳細の表示**\] をクリックします。

5.  削除を有効にするには、\[**QoE データの削除を有効にする**\] を選択します。

6.  \[**QoE データを保持する最大期間 (日数)**\] で、QoE データを保持する必要のある最大日数を選択します。

7.  \[**確定**\] をクリックします。

## Windows PowerShell コマンドレットを使用して QoE の保持を指定するには

Windows PowerShell と **Set-CsQoEConfiguration** コマンドレットを使用して、QoE の保持設定を作成できます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## 特定のロケーションに対して QoE の保持を指定するには

  - このコマンドを実行すると、レドモンド サイトでの QoE データの削除が有効になり、QoE データを 20 日間保持するようにサイトが構成されます。
    
        Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20

## 複数のロケーションに対して QoE の保持を指定するには

  - このコマンドを実行すると、組織で使用されているすべての QoE 構成設定で QoE の保持が構成されます。
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20 

詳細については、[Set-CsQoEConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsQoEConfiguration) コマンドレットのヘルプ トピックを参照してください。

## 関連項目

#### その他のリソース

[Lync Server 2013 での監視の展開](lync-server-2013-deploying-monitoring.md)

