---
title: 'Lync Server 2013: 管理ツールのソフトウェア要件'
TOCTitle: 管理ツールのソフトウェア要件
ms:assetid: 2fb172c3-7b84-4e49-981c-2a17e7a00a29
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg195653(v=OCS.15)
ms:contentKeyID: 48271633
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の管理ツールのソフトウェア要件

 

_**トピックの最終更新日:** 2016-12-08_

このトピックでは、Lync Server 2013 管理ツールをインストールして使用するために、オペレーティング システムの要件以外に必要なソフトウェアについて説明します。

## Microsoft .NET Framework 4.5

Lync Server 2013 には、Microsoft .NET Framework 4.5 の 64 ビット版が必要です。

## Windows PowerShell 3.0

Microsoft Lync Server 2013 のコンポーネントを実行するには、Windows PowerShell 3.0 が必要です。詳細については、「[Lync Server 2013 用の Windows PowerShell 3.0 のインストール](lync-server-2013-installing-windows-powershell-3-0.md)」を参照してください。

## Windows インストーラー バージョン 4.5

Lync Server 2013 では、Windows インストーラー テクノロジを使用して、各種サーバーの役割のインストール、アンインストール、およびメンテナンスを行います。Windows インストーラー バージョン 4.5 は、Windows Server オペレーティング システムの再頒布可能なコンポーネントとして入手できます。Windows インストーラー 4.5 は、Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2 に付属しているため、Lync Server 2013 が実行されているコンピューター用にこのユーティリティをダウンロードする必要はありません (Lync Server 2013 は、Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2 のいずれかが動作するコンピューターにのみインストールできます)。

ただし、管理者ワークステーションに Lync Server 管理シェルまたは Lync Server トポロジ ビルダーをインストールする場合は、Windows インストーラー 4.5 のダウンロードが必要になることがあります。このユーティリティは、Windows 7 と Windows 2008 R2 に付属していますが、それより前のバージョンの Windows オペレーティング システムには付属していません。Windows インストーラー 4.5 は Microsoft ダウンロード センター ([http://go.microsoft.com/fwlink/?linkid=197395\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=197395%26clcid=0x411)) からダウンロードしてください。

## Microsoft Silverlight 5 ブラウザー プラグイン

Lync Server 2013 コントロール パネルは Web ベースのツールであり、最新バージョンの Microsoft Silverlight 5 ブラウザー プラグインをインストールする必要があります。このソフトウェアがインストールされていないか、または古いバージョンがインストールされている場合は、Lync Server 2013 コントロール パネルを起動すると、Lync Server 2013 コントロール パネルによって必要なバージョンのインストールが求められます。

## 関連項目

#### 概念

[Lync Server 2013 でのサーバーおよびツールのオペレーティング システムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)  

#### その他のリソース

[Lync Server 2013 での管理ツールのインフラストラクチャ要件](lync-server-2013-administrative-tools-infrastructure-requirements.md)  
[Lync Server 2013 のセットアップと管理に必要な管理者権限およびアクセス許可](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

