---
title: Microsoft SIP 処理言語 (MSPL) アプリケーションを重要または重要ではないとしてマークする
TOCTitle: Microsoft SIP 処理言語 (MSPL) アプリケーションを重要または重要ではないとしてマークする
ms:assetid: df68fdc6-b7e6-4f07-acdc-0cd4c2c888a1
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg182598(v=OCS.15)
ms:contentKeyID: 48273874
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Microsoft SIP 処理言語 (MSPL) アプリケーションを重要または重要ではないとしてマークする

 

_**トピックの最終更新日:** 2012-11-01_

Microsoft SIP 処理言語 (MSPL) サーバー アプリケーションは、Microsoft Lync 2010 API ではなく MSPL スクリプト言語を使用する、スクリプトのみのアプリケーションです。MSPL サーバー アプリケーションには、重要なアプリケーションとして指定されているものがあります。スクリプトが重要な場合、Lync Server 2013 が起動するために、システムの起動時にこのスクリプトを開始する必要があります。Lync Server の実行中にスクリプトに障害が発生した場合、サーバーは引き続き動作しますが、そのスクリプトへのトラフィックの送信が停止され、イベント ログにエラーが書き込まれます。

Lync Server コントロール パネルを使用して、Microsoft SIP 処理言語 (MSPL) サーバー アプリケーションを重要としてマークしたり、マークを解除したりできます。

すべてのスクリプトでこのオプションがサポートされるわけではありません。 たとえば、DefaultRouting スクリプトは重要としてマークされていますが、このオプションでは DefaultRouting を変更できません。

## MSPL サーバー アプリケーションを重要としてマークするには、またはマークを解除するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**トポロジ**\] をクリックし、\[**サーバー アプリケーション**\] をクリックします。

4.  \[**サーバー アプリケーション**\] ページで、必要があれば列見出しをクリックしてアプリケーションを並べ替えてから、変更するサーバー アプリケーションをクリックします。

5.  \[**アクション**\] をクリックします。

6.  \[**重要としてマーク**\] または \[**重要の指定を解除**\] をクリックします (スクリプトがこのオプションをサポートする場合に実行できます)。

## 関連項目

#### タスク

[Microsoft SIP 処理言語 (MSPL) サーバー アプリケーションの有効化または無効化](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  

#### 概念

[Lync Server 2013 での Microsoft SIP 処理言語 (MSPL) サーバー アプリケーションの表示](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  

#### その他のリソース

[Lync Server 2013 トポロジの管理](lync-server-2013-managing-the-lync-server-topology.md)

