---
title: ダイヤル プラン情報の表示
TOCTitle: ダイヤル プラン情報の表示
ms:assetid: 25ed0112-a8a7-418a-8c2c-580081be692a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ687997(v=OCS.15)
ms:contentKeyID: 49886881
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ダイヤル プラン情報の表示

 

_**トピックの最終更新日:** 2012-11-01_

既存のダイヤル プランの情報を表示するには、以下の手順を実行します。新しいダイヤル プランを作成する場合は、「[Lync Server 2013 でのダイヤル プランの作成](lync-server-2013-create-a-dial-plan.md)」を参照してください。

## Lync Server コントロール パネルからダイヤル プランに関する情報を表示するには

1.  RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「[Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**音声のルーティング**\] をクリックし、\[**ダイヤル プラン**\] をクリックします。

4.  \[**ダイヤル プラン**\] ページで、ダイヤル プラン名をダブルクリックします。
    
    > [!NOTE]
    > 一度に表示できるのは 1 つのダイヤル プランの情報だけです。


## Windows PowerShell のコマンドレットを使用してダイヤル プランを表示する

  - ダイヤル プランは Windows PowerShell コマンドライン インターフェイスと **Get-CsDialPlan** コマンドレットを使用して表示することもできます。このコマンドレットは、Lync Server 2013 管理シェルからも Windows PowerShell のリモート セッションからも実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。
    
    すべてのダイヤル プランに関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、Enter キーを押します。
    
        Get-CsDialPlan
    
    このコマンドを実行すると次のような情報が表示されます。
    
        Identity                 : Global
        Description              :
        DialinConferencingRegion :
        NormalizationRules       : {Description=;
                                   Pattern=^(\d+)$;Translation=$1;Name=
                                   KeepAll;IsInternalExtension=False}
        CountryCode              :
        State                    :
        City                     :
        ExternalAccessPrefix     :
        SimpleName               : DefaultProfile
        OptimizeDeviceDialing    : False

## 関連項目

#### タスク

[Lync Server 2013 でのダイヤル プランの作成](lync-server-2013-create-a-dial-plan.md)  
[Lync Server 2013 でのダイヤル プランの変更](lync-server-2013-modify-a-dial-plan.md)

