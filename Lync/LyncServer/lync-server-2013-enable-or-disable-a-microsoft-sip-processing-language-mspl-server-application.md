---
title: Microsoft SIP 処理言語 (MSPL) サーバー アプリケーションの有効化または無効化
TOCTitle: Microsoft SIP 処理言語 (MSPL) サーバー アプリケーションの有効化または無効化
ms:assetid: b20af38d-224a-4459-991d-0b7eabb3ca7c
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg182573(v=OCS.15)
ms:contentKeyID: 48273305
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Microsoft SIP 処理言語 (MSPL) サーバー アプリケーションの有効化または無効化

 

_**トピックの最終更新日:** 2012-09-21_

Lync Server コントロール パネルを使用して、Lync Server 2013 環境で動作する、Microsoft SIP 処理言語 (MSPL) サーバー アプリケーションを有効または無効にできます。これらのアプリケーションは、Microsoft Lync 2013 Preview API ではなくスクリプト言語を使用する、スクリプトのみのアプリケーションです。

すべてのスクリプトを有効または無効にできるわけではありません。 たとえば、DefaultRouting スクリプトが有効ですが、このオプションでは DefaultRouting を変更できません。

## MSPL サーバー アプリケーションを有効または無効にするには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**トポロジ**\] をクリックし、\[**サーバー アプリケーション**\] をクリックします。

4.  \[**サーバー アプリケーション**\] ページで、必要があれば列見出しをクリックしてアプリケーションを並べ替えてから、変更するサーバー アプリケーションをクリックします。

5.  \[**アクション**\] をクリックします。

6.  \[**アプリケーションを有効にする**\] または \[**アプリケーションを無効にする**\] をクリックします (スクリプトがこのオプションをサポートする場合に実行できます)。

## 関連項目

#### タスク

[Microsoft SIP 処理言語 (MSPL) アプリケーションを重要または重要ではないとしてマークする](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  

#### 概念

[Lync Server 2013 での Microsoft SIP 処理言語 (MSPL) サーバー アプリケーションの表示](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  

#### その他のリソース

[Lync Server 2013 トポロジの管理](lync-server-2013-managing-the-lync-server-topology.md)

