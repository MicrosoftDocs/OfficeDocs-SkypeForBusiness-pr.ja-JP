---
title: 'Lync Server 2013: Active Directory スキーマの準備'
TOCTitle: Active Directory スキーマの準備
ms:assetid: 067726ae-fd3f-4133-a32f-26d2603ac674
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398119(v=OCS.15)
ms:contentKeyID: 48271135
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での Active Directory スキーマの準備

 

_**トピックの最終更新日:** 2016-12-08_

Active Directory ドメイン サービス の準備を始める前に、Windows のメモ帳などのテキスト エディターを使用してスキーマ ファイルを開いたり、「[Lync Server 2013 が使用する Active Directory のスキーマ拡張、クラス、属性](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)」を参照して、Lync Server 2013 用に変更されるすべての Active Directory ドメイン サービス スキーマ拡張を確認したりできます。Lync Server では、次の 4 つのスキーマ ファイルが使用されます。

  - ExternalSchema.ldf (Microsoft Exchange Server との相互運用性を確保するために使用されます)

  - ServerSchema.ldf (Lync Server 2013 のプライマリ スキーマ ファイルです)

  - BackCompatSchema.ldf (以前のリリースのコンポーネントとの相互運用性を確保するために使用されます)

  - VersionSchema.ldf (準備したスキーマのバージョン情報を保持するために使用されます)

以前のリリースから移行しているかどうかや、クリーン インストールを実行しているかどうかに関係なく、すべての .ldf ファイルがスキーマの準備時にインストールされます。 これらのスキーマ ファイルは、上記の一覧に記載されている順序でインストール メディアの \\Support\\schema フォルダーにインストールされます。

Lync Server のスキーマ拡張は、すべてのドメインにレプリケートされるため、ネットワークのトラフィックに影響します。スキーマの準備は、ネットワークの使用率が低いときに実行してください。

> [!NOTE]
> MicrosoftR Office Communicator Mobile 2007 R2 for Java および MicrosoftR Office Communicator Mobile for Nokia 1.0 モバイル クライアントのサポートを Lync Server 2013 の展開に追加する場合、Lync Server 2013 のインストール時に Microsoft Office Communications Server 2007 R2 の Active Directory スキーマを準備する必要があります。必要なソフトウェアとドキュメントについては、<a href="http://go.microsoft.com/fwlink/?linkid=207172%26clcid=0x411" class="uri">http://go.microsoft.com/fwlink/?linkid=207172&amp;clcid=0x411</a> を参照してください。


## ADSI エディター

Active Directory サービス インターフェイス エディター (ADSI エディター) は AD DS の管理ツールです。これを使用すると、スキーマの準備およびレプリケーションを確認できます。

既定では、AD DS の役割をインストールしてサーバーをドメイン コントローラーにするときに ADSI エディターがインストールされます。Windows Server 2008 および Windows Server 2008 R2 の場合、ADSI エディター (adsiedit.msc) はリモート サーバー管理ツール (RSAT) に付属しています。 また、RSAT をドメイン メンバー サーバーまたはスタンドアロン サーバーにインストールすることもできます。 RSAT パッケージは、既定で、Windows のインストール時にこれらのサーバーにコピーされますが、インストールされません。各ツールをインストールするには、サーバー マネージャーを使用します。 ADSI エディターは、\[**役割管理ツール**\]、\[**Active Directory ドメイン サービス ツール**\]、\[**Active Directory ドメイン コントローラー ツール**\] を順に展開すると見つかります。

Windows Server 2003 の場合、ADSI エディターはサポート ツールに付属しています。サポート ツールは、Windows Server 2003 CD の \\SUPPORT\\TOOLS フォルダーから入手するか、「Windows Server 2003 Service Pack 2 32-bit Support Tools」([http://go.microsoft.com/fwlink/?linkid=125770\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=125770%26clcid=0x411)) からダウンロードできます。サポート ツールを製品 CD からインストールする手順については、「Windows サポート ツールをインストールする」([http://go.microsoft.com/fwlink/?linkid=125771\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=125771%26clcid=0x411)) を参照してください。サポート ツールをインストールすると、adsiedit.dll が自動的に登録されます。ただし、ファイルをコンピューターにコピーした場合は、ツールを実行する前に、**regsvr32** コマンドを実行して adsiedit.dll ファイルを登録する必要があります。

## このセクション中

  - [Lync Server 2013 での Active Directory スキーマの準備の実行](lync-server-2013-running-schema-preparation.md)

  - [Lync Server 2013 での Active Directory スキーマのレプリケーションの確認](lync-server-2013-verifying-schema-replication.md)

## 関連項目

#### その他のリソース

[Lync Server 2013 でのフォレストの準備](lync-server-2013-preparing-the-forest.md)  
[Lync Server 2013 のドメインの準備](lync-server-2013-preparing-domains.md)

