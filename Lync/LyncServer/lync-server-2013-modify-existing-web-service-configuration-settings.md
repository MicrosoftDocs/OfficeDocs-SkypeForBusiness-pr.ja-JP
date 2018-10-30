---
title: 既存の Web サービス構成設定の変更
TOCTitle: 既存の Web サービス構成設定の変更
ms:assetid: bd9c7aa5-d31c-4fab-b31d-8baae26b1296
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg182580(v=OCS.15)
ms:contentKeyID: 48273453
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 既存の Web サービス構成設定の変更

 

_**トピックの最終更新日:** 2012-11-01_

\[**Web サービス**\] ページを使用して、Lync Server 2013 関連の Web サーバーと Web サービスにアクセスする場合の認証方式を構成できます。

既存の Web サービス ポリシーを変更するには、次の手順を実行します。

## 既存の Web サービスを変更するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**セキュリティ**\] をクリックし、\[**Web サービス**\] をクリックします。

4.  \[**Web サービス**\] ページで、構成をクリックし、\[**編集**\] をクリックしてから、\[**詳細の表示**\] をクリックします。

5.  \[**Web サービス設定の編集**\] の \[**Windows 認証**\] で、\[**ネゴシエート**\]、\[**統合 Windows 認証**\]、または \[**なし**\] を選択します。

6.  クライアントの機能および環境のサポート状況に応じて、次の中から 1 つ以上選択します。
    
      - \[**PIN 認証を有効にする**\]。PIN 番号を使用してクライアントが承認されるようにします。
    
      - \[**証明書認証を有効にする**\]。プール内のサーバーは、クライアントに対して証明書を発行します。
    
      - \[**証明書チェーンのダウンロードを有効にする**\]。認証証明書を与えられたサーバーがその証明書の証明書チェーンをダウンロードできるようにします。

7.  \[**確定**\] をクリックします。

## 関連項目

#### その他のリソース

[セキュリティの構成](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)

