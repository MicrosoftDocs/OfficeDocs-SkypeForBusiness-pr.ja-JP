---
title: PowerShell を使用する集中ログ サービス構成設定の管理
TOCTitle: PowerShell を使用する集中ログ サービス構成設定の管理
ms:assetid: f455c3aa-0061-413d-bdfb-a3e78f82723d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ721938(v=OCS.15)
ms:contentKeyID: 49887219
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# PowerShell を使用する集中ログ サービス構成設定の管理

 

_**トピックの最終更新日:** 2012-11-01_

集中ログ サービス は、集中ログ サービス コントローラー (CLSController) によって作成されて個々のコンピューターの 集中ログ サービス エージェント (CLSAgent) にコマンドを送信するために使用される設定とパラメーターによって制御および構成されます。このエージェントは送信されたコマンドを処理し、シナリオ、プロバイダー、ログ サイズ、トレース期間、およびフラグの構成を使用して、提供された構成情報に従うトレース ログの収集を開始します。


> [!IMPORTANT]
> 集中ログ サービス 用にリストされている Windows PowerShell のすべてが Lync Server 2013 の内部設置型展開での使用を意図しているわけではありません。以下のコマンドレットは動作するように見えることがありますが、Lync Server 2013 の内部設置型展開で機能するようには設計されていません。 
> <UL>
> <LI>
> <P><STRONG>CsClsRegion コマンドレット:</STRONG> <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsRegion">Get-CsClsRegion</A>、<A href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsRegion">Set-CsClsRegion</A>、<A href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClsRegion">New-CsClsRegion</A>、および <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsClsRegion">Remove-CsClsRegion</A>。</P>
> <LI>
> <P><STRONG>CsClsSearchTerm コマンドレット:</STRONG> <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsSearchTerm">Get-CsClsSearchTerm</A> および <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsSearchTerm">Set-CsClsSearchTerm</A>。</P>
> <LI>
> <P><STRONG>CsClsSecurityGroup コマンドレット:</STRONG> <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsSecurityGroup">Get-CsClsSecurityGroup</A>、<A href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsSecurityGroup">Set-CsClsSecurityGroup</A>、<A href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClsSecurityGroup">New-CsClsSecurityGroup</A>、および <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsClsSecurityGroup">Remove-CsClsSecurityGroup</A>。</P></LI></UL>これらのコマンドレットで定義されている設定は、動作を妨害したり悪影響を起こしたりすることはありませんが、Microsoft Office 365 で使用するように設計されており、内部設置型展開では予期しない結果をもたらします。これは、内部設置型展開ではこれらのコマンドレットが役に立たないという意味ではありませんが、その用途はより高度なトピックであるため、このドキュメントでは扱われません。



## このセクション中

このセクション内のトピックでは、集中ログ サービス 用の構成オプション、パラメーター、および設定を定義しています。集中ログ サービス の構成方法、構成設定の取得方法、シナリオの作成、集中ログ サービス のセキュリティ グループの管理、検索などに関する情報は、以下のトピックに含まれています。

  - [グローバル集中ログ サービス構成、サイト、コンピューターの管理](lync-server-2013-managing-computer-site-and-global-centralized-logging-service-configuration.md)

  - [集中ログ サービス プロバイダーの構成](lync-server-2013-configuring-providers-for-centralized-logging-service.md)

  - [集中ログ サービスのシナリオの構成](lync-server-2013-configuring-scenarios-for-the-centralized-logging-service.md)

## 関連項目

#### 概念

[集中ログサービスの概要](lync-server-2013-overview-of-the-centralized-logging-service.md)  
[集中ログ コマンドレット](https://docs.microsoft.com/en-us/powershell/module/skype/)

