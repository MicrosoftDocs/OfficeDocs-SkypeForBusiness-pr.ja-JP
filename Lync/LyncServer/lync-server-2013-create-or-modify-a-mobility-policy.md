---
title: モビリティ ポリシーの作成または変更
TOCTitle: モビリティ ポリシーの作成または変更
ms:assetid: fc2dfea0-2215-440d-9f4b-7c985da29211
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ721946(v=OCS.15)
ms:contentKeyID: 49887232
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# モビリティ ポリシーの作成または変更

 

_**トピックの最終更新日:** 2013-02-23_

モバイル ユーザーがインスタント メッセージング (IM)、プレゼンス、連絡先などの Lync 機能をサポートしているモバイル デバイスを使用できるよう、モビリティ ポリシーを作成または変更できます。モビリティ ポリシーは、Lync Server 2013 コントロール パネルまたは Lync Server 2013 管理シェルから作成または変更できます。

## Lync Server コントロール パネルからモビリティ ポリシーを作成するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**クライアント**\] をクリックし、\[**モビリティ ポリシー**\] ナビゲーション ボタンをクリックします。

4.  \[**モビリティ ポリシー**\] ページで \[**新規**\] をクリックして、次のいずれかを実行します。
    
    1.  サイト モビリティ ポリシーを作成するには、\[**サイト ポリシー**\] をクリックし、サイトをクリックし、\[**OK**\] をクリックし、既定の設定を確認してから必要に応じて変更を加えます。
    
    2.  ユーザー モビリティ ポリシーを作成するには、\[**ユーザー ポリシー**\] をクリックし、名前を入力し、既定の設定を確認してから必要に応じて変更を加えます。

5.  \[**確定**\] をクリックします。

## Lync Server コントロール パネルからモビリティ ポリシーを変更するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**クライアント**\] をクリックし、\[**モビリティ ポリシー**\] ナビゲーション ボタンをクリックします。

4.  \[**モビリティ ポリシー**\] ページで、既存のモビリティ ポリシーのいずれかをクリックします。

5.  \[**編集**\] メニューの \[**詳細の表示**\] をクリックします。

6.  設定を変更します。

7.  \[**確定**\] をクリックします。

## Windows PowerShell コマンドレットを使用した外部アクセス ポリシーの削除

モビリティ ポリシーは、Windows PowerShell および **New-CsMobilityPolicy** コマンドレットを使って (サイト スコープまたはユーザーごとのスコープで) 作成することもできます。加えて、**Set-CsMobilityPolicy** コマンドレットを使って、グローバル ポリシーを含む任意の既存のポリシーを変更できます。これらのコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## サイト スコープでのモビリティ ポリシーの作成

  - このコマンドは、Redmond サイトのために新しいモビリティ ポリシーを作成します。
    
        New-CsMobilityPolicy -Identity "site:Redmond"
    
    前のコマンドでパラメーターが指定されていない (必須の Identity パラメーターを除く) ので、ポリシーはすべてのプロパティで既定値を使用します。

## ユーザーごとのスコープでのモビリティ ポリシーの作成

  - ユーザーごとのスコープでモビリティ ポリシーを作成するには、ポリシーに固有の Identity を指定します。
    
        New-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

## モビリティ ポリシーの作成時に単一のプロパティ値を変更する

  - 異なるプロパティ値を使用するポリシーを作成するには、適切なパラメーターおよびパラメーター値を含めます。たとえば、このコマンドは \[勤務先から通話\] を無効にするモビリティ ポリシーを作成します。
    
        New-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False

## モビリティ ポリシーの作成時に複数のプロパティ値を変更する

  - 複数のプロパティ値は、複数のパラメーターを含めることによって変更できます。たとえば、このコマンドはモビリティと \[勤務先から通話\] の両方を無効にするポリシーを作成します。
    
        New-CsMobilityPolicy "site:Redmond" -EnableMobility $False -EnableOutsideVoice $False

詳細については、[New-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMobilityPolicy) および [Set-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMobilityPolicy) コマンドレットのヘルプ トピックを参照してください。

## 関連項目

#### タスク

[Lync Server 2013 でのモビリティ ポリシーの構成](lync-server-2013-configuring-mobility-policy.md)

