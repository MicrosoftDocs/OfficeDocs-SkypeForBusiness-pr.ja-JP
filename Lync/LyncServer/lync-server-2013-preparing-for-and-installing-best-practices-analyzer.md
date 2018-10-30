---
title: ベスト プラクティス アナライザーのインストールおよび準備
TOCTitle: ベスト プラクティス アナライザーのインストールおよび準備
ms:assetid: 550613dd-dc08-482e-9980-a3fe187cd162
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg591347(v=OCS.15)
ms:contentKeyID: 48272120
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ベスト プラクティス アナライザーのインストールおよび準備

 

_**トピックの最終更新日:** 2016-12-08_

このトピックで説明するタスクを実行するには、Administrators グループのメンバーとしてログオンする必要があります。

## ベスト プラクティス アナライザーをインストールするためのシステム要件

Lync Server 2013 ベスト プラクティス アナライザーを実行して環境をスキャンするには、コンピューターで次のいずれかのオペレーティング システムの 64 ビット版を実行している必要があります。

  - Windows Server 2008 R2 Service Pack 1 (SP1) Standard オペレーティング システム

  - Windows Server 2008 R2 SP1 Enterprise オペレーティング システム

  - Windows Server 2008 R2 SP1 Datacenter オペレーティング システム

  - Windows Server 2012 Datacenter オペレーティング システム

  - Windows Server 2012 Standard オペレーティング システム

  - Windows Server 2012 Enterprise オペレーティング システム

  - Windows Server 2012 R2 Datacenter オペレーティング システム

  - Windows Server 2012 R2 Standard オペレーティング システム

  - Windows Server 2012 R2 Enterprise オペレーティング システム

  - Windows 8 オペレーティング システム

  - Windows 7 オペレーティング システム

また、以下も実行している必要があります。

  - Microsoft .NET Framework 4.5。Lync Server 2013 の場合、Lync Server 2013 をインストールする前に、64 ビット版の Microsoft .NET Framework 4.5 をサーバーに手動でインストールする必要があります。

  - Lync Server 2013 コア コンポーネント。

  - WMI 下位互換パッケージ。詳しくは、「移行」のドキュメントの「[WMI 下位互換性パッケージをインストールする](install-wmi-backward-compatibility-package.md)」をご覧ください。

  - Windows PowerShell 3.0。詳しくは、「展開」のドキュメントの「[Lync Server 2013 用の Windows PowerShell 3.0 のインストール](lync-server-2013-installing-windows-powershell-3-0.md)」をご覧ください。

Lync Server 2013 コア コンポーネントまたは WMI 下位互換パッケージを実行していなくても、サポートされているオペレーティング システムを実行しているコンピューターであれば、ベスト プラクティス アナライザーをインストールできます。ただし、このようなコンピューターでは、ベスト プラクティス アナライザーを使用してスキャンを実行することはできず、レポートの表示のみとなります。

## インストール対象のコンピューターの選択

Lync Server 2013 ベスト プラクティス アナライザーは、Lync Server 2013 の管理専用のコンピューターにインストールすることをお勧めします。Lync Server 2013 を実行しているサーバーまたは Lync Server 2013 管理ツールを実行している管理コンピューターにこのツールをインストールできます。Lync Server を実行しているサーバーにインストールした場合は、ツールでそのサーバーだけをスキャンすることをお勧めします。

## ベスト プラクティス アナライザーのインストール

Lync Server 2013 のベスト プラクティス アナライザーは、[http://go.microsoft.com/fwlink/?linkid=266539\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=266539%26clcid=0x411) でダウンロードできます。

ベスト プラクティス アナライザーをインストールするには、ツールをインストールするコンピューターで Microsoft インストーラー ファイル (RtcBPA.msi) を起動し、画面の指示に従います。プログラム ファイルは、既定で *\<システム ドライブ\>*\\Program Files\\Lync Server 2013\\BPA にインストールされます。

