---
title: 'Lync Server 2013: スキーマの準備の実行'
TOCTitle: スキーマの準備の実行
ms:assetid: 9d02bdb1-ff29-417a-bcce-b068b31207d8
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412729(v=OCS.15)
ms:contentKeyID: 48272985
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での Active Directory スキーマの準備の実行

 

_**トピックの最終更新日:** 2016-12-08_

セットアップまたは Lync Server 管理シェル コマンドレットを使用して Active Directory スキーマを準備することができます。Active Directory スキーマを拡張するコマンドレットは **Install-CsAdServerSchema** です。

> [!NOTE]
> スキーマの準備コマンドレット ( <strong>Install-CsAdServerSchema</strong>) は、スキーマ マスターにアクセスする必要があります。それには、リモート レジストリ サービスが実行され、リモート レジストリ キーが有効になっている必要があります。リモート レジストリ サービスをスキーマ マスター上で有効にすることができない場合は、スキーマ マスター上でローカルにコマンドレットを実行できます。レジストリのリモート アクセスの詳細については、Microsoft サポート技術情報の記事 314837「レジストリへのリモート アクセスを管理する方法」( <a href="http://go.microsoft.com/fwlink/?linkid=125769%26clcid=0x411" class="uri">http://go.microsoft.com/fwlink/?linkid=125769&amp;clcid=0x411</a>) を参照してください。


スキーマの準備が完了したら、スキーマ パーティションがレプリケートされたことを手動で確認してから、フォレストの準備に進んでください。詳細については、「[Lync Server 2013 での Active Directory スキーマのレプリケーションの確認](lync-server-2013-verifying-schema-replication.md)」を参照してください。

## セットアップを使用して、現在のフォレストのスキーマを準備するには

1.  Schema Admins グループのメンバーとして、さらに、スキーマ マスターにおける管理者権限を使用して、フォレスト内のサーバーにログオンします。

2.  Lync Server 2013 のインストール フォルダーまたはメディアから、Setup.exe を実行して展開ウィザードを起動します。

3.  Microsoft Visual C++ (再頒布可能) のインストールを要求するメッセージが表示されたら、\[**はい**\] をクリックします。

4.  Lync Server 2013 セットアップ ダイアログ ボックスが、 Lync Server ファイルをインストールする場所を求めるメッセージを表示します。既定の場所を選択するか、または好みの場所を \[**参照**\] で選択し、\[**インストール**\] をクリックします。

5.  \[使用許諾契約書\] ページで \[**使用許諾契約書に同意します**\] チェック ボックスをオンにし、\[**OK**\] をクリックします。

6.  インストーラーが Lync Server コア コンポーネントをインストールします。

7.  展開ウィザードの準備ができたら、\[**Active Directory の準備**\] をクリックし、展開状態が判別されるまで待機します。

8.  \[**ステップ 1: スキーマの準備**\] で、\[**実行**\] をクリックします。

9.  \[**スキーマの準備**\] ページで、\[**次へ**\] をクリックします。

10. \[**コマンドの実行**\] ページで \[**タスク状態: 完了**\] を見つけて、\[**ログの表示**\] をクリックします。

11. \[**アクション**\] 列で \[**スキーマの準備**\] を展開します。各タスクの末尾に \[**\<成功\>**\] の実行結果が表示されているかどうかを調べ、スキーマの準備が正常に完了したことを確認します。その後、ログを閉じて \[**完了**\] をクリックします。

12. Active Directory レプリケーションが完了するのを待機するか、レプリケーションを強制的に実行します。

13. スキーマの変更が他のすべてのドメイン コントローラーにレプリケートされたことを手動で確認します。詳細については、「[Lync Server 2013 での Active Directory スキーマのレプリケーションの確認](lync-server-2013-verifying-schema-replication.md)」を参照してください。

## コマンドレットを使用して現在のフォレストのスキーマを準備するには

1.  Schema Admins グループのメンバーとして、さらに、スキーマ マスターにおける管理者の権限を使用して、フォレスト内のコンピューターにログオンします。

2.  Lync Server コア コンポーネントを次の手順でインストールします。
    
    1.  Lync Server 2013 のインストール フォルダーまたはメディアから、Setup.exe を実行して Lync Server 展開ウィザードを起動します。
    
    2.  Microsoft Visual C++ (再頒布可能) のインストールを要求するメッセージが表示されたら、\[**はい**\] をクリックします。
    
    3.  Lync Server 2013 セットアップ ダイアログ ボックスが、 Lync Server ファイルをインストールする場所を求めるメッセージを表示します。既定の場所を選択するか、または好みの場所を \[**参照**\] で選択し、\[**インストール**\] をクリックします。
    
    4.  \[使用許諾契約書\] ページで \[**使用許諾契約書に同意します**\] チェック ボックスをオンにし、\[**OK**\] をクリックします。インストーラーが Lync Server 2013 コア コンポーネントをインストールします。

3.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

4.  次のコマンドレットを実行します。
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    Ldf パラメーターを指定しない場合、既定値は、レジストリから読み取る Lync Server 2013 のインストール パスです。
    
    次に例を示します。
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  次のコマンドレットを使用し、スキーマの準備が完了したことを確認します。
    
        Get-CsAdServerSchema 
    
    スキーマの準備が正常に完了した場合、このコマンドレットは **SCHEMA\_VERSION\_STATE\_CURRENT** の値を返します。

6.  Active Directory レプリケーションが完了するのを待機するか、レプリケーションを強制的に実行します。

7.  スキーマの変更が他のすべてのドメイン コントローラーにレプリケートされたことを手動で確認します。詳細については、「[Lync Server 2013 での Active Directory スキーマのレプリケーションの確認](lync-server-2013-verifying-schema-replication.md)」を参照してください。

## 関連項目

#### タスク

[Lync Server 2013 での Active Directory スキーマのレプリケーションの確認](lync-server-2013-verifying-schema-replication.md)  

#### 概念

[Lync Server 2013 での Active Directory スキーマの準備](lync-server-2013-preparing-the-active-directory-schema.md)

