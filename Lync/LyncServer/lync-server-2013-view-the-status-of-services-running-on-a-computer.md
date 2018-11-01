---
title: Lync Server 2013 でのコンピューターで実行されているサービスの状態の表示
TOCTitle: Lync Server 2013 でのコンピューターで実行されているサービスの状態の表示
ms:assetid: f41918e7-4c02-431e-840a-88a1f36ae499
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg182606(v=OCS.15)
ms:contentKeyID: 48273985
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのコンピューターで実行されているサービスの状態の表示

 

_**トピックの最終更新日:** 2013-02-22_

Lync Server 2013 コントロール パネルを使用して、Lync Server トポロジ内の特定のコンピューター上で実行されているすべてのサービスを表示し、各サービスの状態を確認できます。

## コンピューターで実行されているサービスの状態を表示するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**トポロジ**\] をクリックします。

4.  \[**状態**\] ページで、必要に応じてリストを並べ替えまたは検索して対象のコンピューターを見つけ、そのコンピューター名をクリックします。

5.  次のいずれかの操作を行います。
    
      - コンピューターで実行されているサービスの最新状態を表示するには、\[**サービス状態の取得**\] をクリックします。
    
      - コンピューターで実行されている特定のサービスの一覧および各サービスの状態を表示するには、\[**プロパティ**\] をクリックし、\[**閉じる**\] をクリックして一覧に戻ります。

## Lync Server 管理シェル コマンドレットによるサービス状態の表示

Lync Server 管理シェルおよび **Get-CsWindowsService** コマンドレットを使用することによっても、サービス状態を表示できます。このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## サービス状態を表示するには

  - コンピューターでサービス状態を表示するには、Lync Server 管理シェルで次のようなコマンドを入力して、Enter キーを押します。
    
        Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
    
    このコマンドは、次のような情報を返します。
    
        RoleName                                  Status
        --------                                  ------
        {W3SVC}                                   Running
        {CentralManagement}                       Running
        {ClsAgent}                                Running
        {Registrar, UserServer, EdgeServer}       Running
        {ApplicationServer}                       Running
        {ConferencingServer}                      Running
        {MediationServer}                         Running

詳細については、「[Get-CsWindowsService](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsWindowsService)」を参照してください。

## 関連項目

#### その他のリソース

[Lync Server 2013 でのデバイス、電話、クライアント アプリケーションの管理](lync-server-2013-managing-devices-phones-and-client-applications.md)

