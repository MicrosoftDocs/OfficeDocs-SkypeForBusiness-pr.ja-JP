---
title: Lync Server 2013 管理ツールを開く
TOCTitle: Lync Server 2013 管理ツールを開く
ms:assetid: 8c58de94-9e0a-4368-9e14-9afcaa1142d0
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg195741(v=OCS.15)
ms:contentKeyID: 48272780
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 管理ツールを開く

 

_**トピックの最終更新日:** 2012-06-28_

このトピックでは、Lync Server 2013 トポロジの展開、構成、またはトラブルシューティングを行う管理ツールを開く手順について説明します。

  - 展開ウィザード

  - トポロジ ビルダー

  - Lync Server コントロール パネル

  - Lync Server 管理シェル

## 展開ウィザード

次の手順を使用して、Lync Server 2013 コンポーネント ファイルの追加または削除を行う展開ウィザードをローカルで開始します。

## Lync Server 2013 展開ウィザードを開始するには

1.  Lync Server 展開ウィザードがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。

2.  \[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 展開ウィザード**\] の順にクリックします。

## トポロジ ビルダー

次の手順を使用して、Lync Server 2013 トポロジに展開するサーバーを定義するトポロジ ビルダーを開きます。

## Lync Server 2013 トポロジ ビルダーを開いてトポロジを設計するには

1.  トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。
    
    > [!NOTE]
    > トポロジを定義するには、ローカルの Users グループのメンバーであるアカウントを使用します。ただし、Lync Server 2013 をサーバーにインストールするのに必要なトポロジの読み取り、公開、または有効化を行うには、RTCUniversalServerAdmins グループの Domain Admins グループのメンバーであるアカウントを使用する必要があります。また、このアカウントには、アーカイブ ファイル ストアで使用するファイル共有に対して、フル コントロールのアクセス許可 (読み取り、書き込み、および変更) を持っている必要があります。これで、トポロジ ビルダーは必要な随意アクセス制御リスト (DACL) を構成できるようになります。または、上記と同等のユーザー権限を持つアカウントを使用する必要があります。


2.  トポロジ ビルダーを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server トポロジ ビルダー**\] の順にクリックします。

## Lync Server 2013 コントロール パネル

次の手順を使用して、サーバーの構成を管理する Lync Server 2013 コントロール パネルを開きます。

> [!NOTE]
> CsAdministrator 役割に割り当てられているユーザー アカウントを使用することで、Lync Server 2013 コントロール パネルのすべてのタスクを実行できます。特定の管理タスクを実行するには、実行する必要があるタスクに応じて、他の役割を使用して Lync Server 2013 コントロール パネルにログオンできます。たとえば、CSArchivingAdministrator を使用することで、Lync Server 2013 コントロール パネルのアーカイブを管理できます。役割の詳細については、「計画」のドキュメントの「<a href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 での役割ベースのアクセス制御の計画</a>」を参照してください。特定のタスクを実行する場合に使用できる役割の詳細については、該当タスクのドキュメントを参照してください。


## 組織のファイアウォールの内側にあるコンピューターから Lync Server 2013 コントロール パネルを開くには

1.  CsAdministrator の役割、またはタスクを実行するのに適切なユーザー権限とアクセス許可を持つその他の役割に割り当てられているユーザー アカウントから、内部展開内の任意のコンピューター (1,024 x 768 以上の画面解像度が必要) にログオンします。
    

    > [!IMPORTANT]
    > 管理の簡易 URL を構成済みの場合は、組織のファイアウォール内のコンピューター上で実行されているインターネット ブラウザーから Lync Server 2013 コントロール パネルにアクセスできます。管理の簡易 URL を構成する方法の詳細については、計画に関するドキュメントの「<A href="lync-server-2013-planning-for-simple-urls.md">Lync Server 2013 での簡単な URL の計画</A>」および展開に関するドキュメントの「<A href="lync-server-2013-edit-or-configure-simple-urls.md">Lync Server 2013 での簡単な URL の編集または構成</A>」を参照してください。



2.  ブラウザー ウィンドウを開き、組織に対して構成されている管理 URL を入力します。

## Lync Server 2013 を実行するコンピューターで Lync Server 2013 コントロール パネルを開くには

1.  CsAdministrator 役割のメンバー、またはタスクを実行するための適切なユーザー権限とアクセス許可を持つその他の役割のメンバーであるユーザー アカウントから、Lync Server 2013 または少なくとも Lync Server 2013 管理ツールがインストールされているコンピューターにログオンします。設定を構成するには、コンピューターの画面解像度が 1,024 x 768 以上である必要があります。

2.  次の手順で Lync Server 2013 コントロール パネル を開始します。\[**スタート**\] をクリックし、\[**すべてのプログラム**\] をクリックし、\[**管理ツール**\]、\[**Microsoft Lync Server 2013**\] の順にポイントして、\[**Lync Server 2013 コントロール パネル**\] をクリックします。

## Lync Server 2013 管理シェル

次の手順を使用して、コマンド ラインで環境内のサーバー、ユーザー、クライアント、およびデバイスを管理する Lync Server 2013 管理シェルを開きます。

> [!NOTE]
> CsAdministrator 役割に割り当てられているユーザー アカウントを使用することで、Lync Server 2013 管理シェルのすべてのタスクを実行できます。特定の管理タスクを実行するには、実行する必要があるタスクに応じて、他の役割を使用してログオンできます。たとえば、CSArchivingAdministrator を使用することで、アーカイブ管理に管理するコマンドレットを実行できます。役割の詳細については、「計画」のドキュメントの「<a href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 での役割ベースのアクセス制御の計画</a>」を参照してください。特定のコマンドレットを実行する場合に使用できる役割の詳細については、該当コマンドレットのドキュメントを参照してください。<br />
> コマンドレットに応じて、RTCUniversalServerAdmins、RTCUniversalUserAdmins、または RTCUniversalReadOnlyAdmins の各グループのユーザー アカウントを使用して、特定のコマンドレットを実行することもできます。


## Lync Server 2013 管理シェルを開くには

  - Lync Server 2013 管理シェルではなく Windows PowerShell ウィンドウを開くと、既定では Lync Server 2013 コマンドレットを実行できません。Windows PowerShell 内から Lync Server 2013 のコマンドレットを実行するには、まず Windows PowerShell のコマンド プロンプトで以下のように入力します。
    
    `Import-Module Lync`

  - Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

## 関連項目

#### タスク

[Lync Server 2013 管理ツールをインストールする](lync-server-2013-install-lync-server-administrative-tools.md)  

#### 概念

[Lync Server 2013 管理ツール](lync-server-2013-lync-server-administrative-tools.md)

