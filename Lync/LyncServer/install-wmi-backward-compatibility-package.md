---
title: WMI 下位互換性パッケージをインストールする
TOCTitle: WMI 下位互換性パッケージをインストールする
ms:assetid: 38797fbd-06a0-4008-b099-158e7b5d7703
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204816(v=OCS.15)
ms:contentKeyID: 48271771
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# WMI 下位互換性パッケージをインストールする

 

_**トピックの最終更新日:** 2012-10-02_

WMI 下位互換パッケージをインストールせずにトポロジ ビルダー マージ ウィザードを実行しようとすると、次のエラーが表示されます。

![WMI エラー メッセージ](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "WMI エラー メッセージ")

WMI 下位互換パッケージをインストールせずに **Merge-CsLegacytopology** コマンドレットを実行しようとすると、次のエラーが表示されます。

![Windows PowerShell WMI プロバイダー エラー](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Windows PowerShell WMI プロバイダー エラー")

WMI 下位互換パッケージをインストールするには

1.  インストール メディアで \\SETUP\\AMD64\\SETUP\\OCSWMIBC.MSI へ移動します。

2.  OCSWMIBC.MSI をインストールします。
    

    > [!IMPORTANT]
    > OCSWMIBC.msi は、トポロジ ビルダー マージ ウィザードが実行されているコンピューターにインストールする必要があります。ただし、トポロジ内のすべてのフロントエンド サーバーに OCSWMIBC.msi をインストールすることをお勧めします。

    

    > [!IMPORTANT]
    > OCSWMIBC.msi は、Lync Server 2013 コア コンポーネントと Lync Server 2013 管理シェルがインストールされていて、Office Communications Server 2007 R2 トポロジ (Active Directory Domain Service (AD DS) および SQL Server に対する WMI プロバイダー) にアクセスできるコンピューターであれば、ドメイン内のどのコンピューターにインストールしてもかまいません。


