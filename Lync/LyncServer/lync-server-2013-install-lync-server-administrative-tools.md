---
title: 'Lync Server 2013: Lync Server 管理ツールをインストールする'
TOCTitle: Lync Server 管理ツールをインストールする
ms:assetid: 842b85e4-2eeb-464f-b1c1-ceb8cc04f8d5
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398665(v=OCS.15)
ms:contentKeyID: 48272757
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 管理ツールをインストールする

 

_**トピックの最終更新日:** 2013-02-21_

This topic describes how to install the administrative tools you need to use to deploy and manage Lync Server 2013. The administrative tools are installed by default on each server running Lync Server 2013. また、専用の管理コンソールなど、他のコンピューター上に管理ツールをインストールすることもできます。 We strongly recommend that you install the administrative tools on a computer that is in the same domain or forest as the Lync Server 2013 deployment you are creating because by doing so you make sure that Active Directory ドメイン サービス preparation steps are already complete, which enables you to use the administrative tools on that computer later to publish your topology.

Lync Server 2013 管理ツールをインストールまたは使用する前に、インフラストラクチャ、オペレーティング システム、ソフトウェア、および管理者権限の各要件を見直してください。インフラストラクチャの要件の詳細については、「 [Lync Server 2013 での管理ツールのインフラストラクチャ要件](lync-server-2013-administrative-tools-infrastructure-requirements.md)」を参照してください。 Lync Server 2013 管理ツールをインストールする際のオペレーティング システムとソフトウェアの要件の詳細については、「 [Lync Server 2013 でのサーバーおよびツールのオペレーティング システムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)」、「 [Lync Server 2013 の追加ソフトウェア要件](lync-server-2013-additional-software-requirements.md)」、および「 [Lync Server 2013 の追加サーバー サポートおよび要件](lync-server-2013-additional-server-support-and-requirements.md)」を参照してください。管理ツールをインストールおよび使用するのに必要なユーザー権限およびアクセス許可の詳細については、「 [Lync Server 2013 のセットアップと管理に必要な管理者権限およびアクセス許可](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)」を参照してください。


> [!IMPORTANT]
> 組織でインターネット インフォメーション サービス (IIS) およびすべての Web サービスをシステム ドライブ以外のドライブに配置する必要がある場合は、[セットアップ] ダイアログ ボックスで Lync Server ファイルのインストール先パスを変更できます。OCSCore.msi など、セットアップ ファイルをこのパスにインストールすると、残りの Lync Server 2013 ファイルもこのドライブに展開されます。



## Lync Server 2013 管理ツールをインストールするには

1.  管理ツールのインストール先のコンピューターにローカル管理者 (最小要件) としてログオンします。Windows Vista または Windows 7 オペレーティング システムの標準ユーザーとしてログオンしており、ユーザー アカウント制御 (UAC) が有効になっている場合は、ローカル管理者または同等のドメイン ユーザーの名前とパスワードの入力を求められます。

2.  コンピューターにインストール メディアを配置し、\\Setup\\amd64\\Setup.exe をダブルクリックします。

3.  Microsoft Visual C++ 2008 (再頒布可能) のインストールを指示されたら、\[ **はい** \] をクリックします。

4.  \[ **Microsoft Lync Server 2013 のインストール先** \] ページで \[ **OK** \] をクリックします。ファイルを他の場所にインストールする必要がある場合は、このパスを他の場所またはドライブに変更します。
    

    > [!IMPORTANT]
    > 組織で インターネット インフォメーション サービス (IIS) およびすべての Web サービスをシステム ドライブ以外のドライブに配置する必要がある場合は、[セットアップ] ダイアログ ボックスで Lync Server 2013 ファイルのインストール先パスを変更できます。このパスに OCSCore.msi など、セットアップ ファイルをインストールすると、残りの Lync Server 2013 ファイルもこのドライブに展開されます。



5.  \[ **使用許諾契約書** \] ページでライセンス条項を確認し、\[ **同意する** \] をクリックしてから \[ **OK** \] をクリックします。続行するにはこのステップが必要です。

6.  \[ **Microsoft Lync Server 2013 - 展開ウィザード** \] ページで、\[ **管理ツールのインストール** \] をクリックします。

7.  インストールが正常に完了したら、\[ **終了** \] をクリックします。

## 関連項目

#### タスク

[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)  

#### 概念

[Lync Server 2013 管理ツール](lync-server-2013-lync-server-administrative-tools.md)

