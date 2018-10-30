---
title: 'Lync Server 2013: SIP/CSTA ゲートウェイの IP アドレスの定義'
TOCTitle: SIP/CSTA ゲートウェイの IP アドレスの定義
ms:assetid: ae944057-3ad6-4474-a09b-81a3d27bd50f
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg602125(v=OCS.15)
ms:contentKeyID: 48273269
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での SIP/CSTA ゲートウェイの IP アドレスの定義

 

_**トピックの最終更新日:** 2012-09-21_

Lync Server が、リモート通話コントロールのために展開した SIP/CSTA ゲートウェイに、伝送制御プロトコル (TCP) 接続を使用して接続する場合は、 トポロジ ビルダーでゲートウェイの IP アドレスを定義する必要があります。トランスポート層セキュリティ (TLS) 接続をサポートするゲートウェイの場合、このステップは必要ありません。TLS をサポートするゲートウェイでは、この手順を省略し、「[Lync Server 2013 でのリモート通話コントロールの Lync ユーザーの有効化](lync-server-2013-enable-lync-users-for-remote-call-control.md)」の手順に従って、リモート通話コントロールの展開を続行することができます。

## トポロジ ビルダーを使用して SIP/CSTA ゲートウェイの IP アドレスを定義するには

1.  トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。

2.  トポロジ ビルダーを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server トポロジ ビルダー**\] の順にクリックします。

3.  既存のトポロジをダウンロードするオプションを選択します。

4.  \[**信頼されたアプリケーション サーバー**\] ノードを展開します。

5.  「[Lync Server 2013 でリモート通話コントロールの信頼済みアプリケーション エントリを構成する](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)」に従って作成した、信頼されたアプリケーション プールを右クリックして、\[**プロパティの編集**\] をクリックします。

6.  \[**このプールへの構成データのレプリケーションを有効にする**\] チェック ボックスをオフにします。

7.  \[**サービスの使用を選択した IP アドレスに限定する**\] をクリックします。既定の設定は \[**すべての構成済み IP アドレスの使用**\] です。

8.  \[**プライマリ IP アドレス**\] テキスト ボックスに、SIP/CSTA ゲートウェイの IP アドレスを入力します。

9.  中央管理ストアでトポロジを更新するには、コンソール ツリーの \[**Lync Server**\] をクリックし、\[**操作**\] ウィンドウで \[**公開**\] をクリックします。

## 関連項目

#### タスク

[Lync Server 2013 でのリモート通話コントロールの静的ルートの構成](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[Lync Server 2013 でリモート通話コントロールの信頼済みアプリケーション エントリを構成する](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)

