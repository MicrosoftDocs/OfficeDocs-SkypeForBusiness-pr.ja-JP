---
title: 'Lync Server 2013: IIS の保護'
TOCTitle: Lync Server 2013 での IIS の保護
ms:assetid: a67171a6-6703-4e09-abb3-35d335bb674e
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Dn518332(v=OCS.15)
ms:contentKeyID: 60498594
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での IIS の保護

 

_**トピックの最終更新日:** 2013-12-05_

Microsoft Office Communications Server 2007 および Microsoft Office Communications Server 2007 R2 では、インターネット インフォメーション サービス (IIS) が標準のユーザー アカウントで実行されていました。このため、アカウントのパスワードが期限切れになると Web サービスが失われるという問題が発生する可能性がありました。この問題は多くの場合、診断が困難でした。パスワードの期限切れの問題を防ぐため、Microsoft Lync Server 2013 では、IIS を実行するサイト内の全コンピューターの認証プリンシパルとして機能できる (実際には存在しないコンピューター用の) コンピューター アカウントを作成することができます。これらのアカウントは Kerberos 認証プロトコルを使用するため、アカウントは Kerberos アカウントと呼ばれ、新しい認証プロセスが Kerberos Web 認証として認識されます。これにより、1 つのアカウントを使用してすべての IIS サーバーを管理することができます。

この認証プリンシパルでサーバーを実行するには、最初に New-CsKerberosAccount コマンドレットを使用してコンピューター アカウントを作成し、次にこのアカウントを 1 つ以上のサイトに割り当てます。この割り当てを行った後、Enable-CsTopology コマンドレットを実行すると、このアカウントと Lync Server 2013 サイト間の関連付けができるようになります。特に重要なのは、これによって必要なサービス プリンシパル名 (SPN) が Active Directory ドメイン サービス (AD DS) 内に作成されることです。 SPN は、クライアント アプリケーションが特定のサービスを検出するためのものです。 詳細については、「操作」のドキュメントの「[New-CsKerberosAccount](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsKerberosAccount)」を参照してください。

## ベスト プラクティス

IIS のセキュリティを強化するために、IIS 用の Kerberos アカウントを実装することをお勧めします。Kerberos アカウントを実装しない場合、IIS は標準のユーザー アカウントで実行されます。

