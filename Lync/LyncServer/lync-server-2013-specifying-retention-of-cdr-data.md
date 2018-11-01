---
title: CDR データの保持期間の指定
TOCTitle: CDR データの保持期間の指定
ms:assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg182581(v=OCS.15)
ms:contentKeyID: 48273475
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# CDR データの保持期間の指定

 

_**トピックの最終更新日:** 2013-02-23_

既定では、通話詳細記録 (CDR) データは 60 日後に削除されます。 \[**通話詳細記録**\] ページの設定を使用して、このデータを既定よりも長期間、または短期間保持できます。 CDR を無効にすると、CDR を有効にする前に取得されたデータも削除の対象になります。

> [!NOTE]
> CDR と QoE (Quality of Experience) を構成して、データが同じ日数保持されるようにする必要があります。 通話詳細記録 (CDR) 内の各通話は、監視サーバー レポートの Web ページから取得できます。これには、CDR 情報と QoE 情報の両方が含まれます。 削除期間が CDR と QoE で異なると、CDR データのみ含む通話がある一方で、QoE データのみ含む通話があることになります。


CDR データの削除設定を構成するには、次の手順を実行します。

## CDR データの保持期間を指定するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで、\[**監視とアーカイブ**\] をクリックし、\[**通話詳細記録**\] をクリックします。

4.  \[**通話詳細記録**\] ページで、表から適切なサイトをクリックし、\[**編集**\] をクリックしてから、\[**詳細の表示**\] をクリックします。

5.  削除を有効にするには、\[**CDR の削除を有効にする**\] を選択します。

6.  \[**CDR を保持する最大期間 (日数)**\] で、通話詳細記録を保持する必要のある最大日数を選択します。

7.  \[**エラー報告データの最大保持期間 (日)**\] で、 エラー報告を保持する必要のある最大日数を選択します。

8.  \[**確定**\] をクリックします。

## Lync Server 管理シェル コマンドレットを使用して CDR の保持を指定するには

Windows PowerShell と Set-CsCdrConfiguration コマンドレットを使用して、CDR の保持設定を作成できます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## 特定のロケーションに対して CDR の保持を指定するには

  - このコマンドを実行すると、レドモンド サイトでの CDR データの削除が有効になり、CDR データとエラー レポートの両方を 20 日間保持するようにサイトが構成されます。
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20

## 複数のロケーションに対して CDR の保持を指定するには

  - このコマンドを実行すると、組織内で使用されているすべての CDR 構成設定に対して CDR の保持が構成されます。
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20

詳細については、[Set-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCdrConfiguration) コマンドレットのヘルプ トピックを参照してください。

## 関連項目

#### その他のリソース

[通話詳細記録 (CDR)](lync-server-2013-call-detail-recording-cdr.md)

