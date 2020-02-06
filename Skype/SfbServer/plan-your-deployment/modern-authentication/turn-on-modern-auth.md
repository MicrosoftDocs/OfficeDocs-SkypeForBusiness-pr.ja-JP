---
title: 内部および外部のネットワークに対して従来の認証方法を無効にする計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: ''
description: この記事では、ビジネスの内部および外部で使用される認証方法を管理者が制御できるコマンドレットについて説明します。 管理者は、内部または外部のネットワークに認証方法を有効または無効にすることができます。
ms.openlocfilehash: 21aacd6514ee9e47087906292564eea7aede7ead
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815815"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a>内部および外部のネットワークに対して従来の認証方法をオフにすることを計画しています。

> [!NOTE]
> この記事をお読みになる場合は、サポートされている先進認証トポロジ、ADAL、先進認証構成について既に理解している必要があります。ただし、そうしない場合は、次の記事を参照してください。 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal)
  
先進認証は、2要素認証や証明書ベース認証などのセキュリティ保護された認証方法を実現するだけでなく、ユーザー名やパスワードを必要とせずに、ユーザーの認証を実行することができます。 とても便利です。

この記事では、Skype for Business Server のサービス拒否 (DOS) 攻撃に悪用された可能性のあるものを、ネットワークに対して外部、内部、またはその両方の認証に使用しないようにすることを目的としています。 たとえば、DOS 攻撃を止めるための適切な方法の1つとして、Windows 統合認証を無効にする方法があります (NTLM と Kerberos を含む)。 NTLM をオフにして証明書ベースの認証を使用すると、パスワードが漏洩するのを防ぐことができます。 これは、NTLM はパスワード資格情報を使用してユーザーを認証するのに対し、証明書ベースの認証は先進認証によって有効になっているためです。 つまり、DOS 攻撃を軽減するために最適なオプションの1つとして、NTLM をブロックし、代わりに証明書ベースの認証のみを使うことができます。

さあ、始めましょう。

## <a name="what-would-you-be-changing"></a>何を変更しますか? 

これらのコマンドレットは、SIP と Web サービスの両方のアクセスポイントで機能します。 この2つのチャネルでは、さまざまなアクセス方法を使用していますが、NTLM と Kerberos から匿名アクセスに適用されているすべての標準的な方法が考慮されています。

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a>Get と Set の設定コマンドレットを取得する方法

これらのコマンドレットは、Microsoft Skype for Business Server 2015 の2018年7月の累積更新プログラム (6.0.9319.534) の投稿のみにインストールされています。そのため、Skype for Business server 用に展開できるさまざまなトポロジが用意されています。

## <a name="topologies"></a>トポロジー

このシナリオでは、これらはサポートされているトポロジであることに注意する必要があります。 たとえば、メソッドをブロックするためのサポートについては、以下の型のいずれかを構成する必要があります。 

> [!IMPORTANT]
> 以下の表と説明では、*先進認証*は__MA__として省略されており、 *Windows 統合認証*は__Win__と略記されています。 Windows 統合認証は、NTLM と Kerberos 認証という2つの方法で構成されます。 表を正しく読むには、これを知っておく必要があります。


|       |的  |内部  |パラメーター  |
|---------|:---------|:---------|---------|
|__「1」と入力__   |  MA + Win       | MA + Win         |  AllowAllExternallyAndInternally       |
|__「2」と入力__   |  100       | MA + Win         | 外部のブロック        |
|__「3」と入力します。__   |  100       | 100        | BlockWindowsAuthExternallyAndInternally        |
|__「4」と入力__   |  100       | Win        | BlockWindowsAuthExternallyAndModernAuthInternally    |
|__「5」と入力__   |  MA + Win       | Win        | BlockModernAuthInternally         |

__1 の説明を入力します。__ これは、Skype for Business __Server で MA をオンに__した場合の既定のシナリオです。 つまり、MA が構成されている場合は、これが*出発点*となります。

__「2」と入力します。__ このトポロジでは、NTLM が*外部*でブロックされますが、ntlm または KERBEROS (ADAL をサポートしていないクライアントの場合) は*内部*で動作することができます。 クライアントが ADAL をサポートしている場合は、内部で MA が使用されます。

__「3の説明」と入力します。__ このトポロジには、すべてのユーザーに対して MA が必要です。 すべての ADAL 対応クライアントはこのトポロジで動作します。たとえば、証明書ベースの Auth でパスワードの使用を無効にした場合、パスワードは利用できません。

__「4」の説明を入力します。__ このトポロジは、NTLM を*外部*および MA に内部的にブロックします。 すべての*クライアント*で*内部的*に (ADAL 対応クライアントでも) 従来の認証方法を使用できるようにします。

__Type 5 説明:__ *外部*では、最新の adal クライアントは MA を使用し、adal をサポートしていないすべてのクライアントは従来の認証方法を使用します。 ただし、 ** *すべてのクライアント*は従来の認証 (すべての ADAL 対応クライアントを含む) を使用します。

使用可能なオプションでパスワードの保護の目標を把握するのは非常に簡単です。 理想的な状況としては、(証明書ベースの認証を構成するなど) MA を外部で使用して、DOS 攻撃を回避することをお勧めします。 最新のクライアントに対して内部で利用すると、Skype for Business Server の DOS 攻撃に関するネットワークの将来性を証明することになります。

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a>グローバルレベルで Set-CsAuthConfig を使用する理由

レジストラー `Set-CsAuthConfig`と Web サービスの役割の両方での、コマンドレットの効果の構成。

このコマンドレットは、Skype for Business server のグローバルレベルで実行することを目的としています。 プールレベルで実行する*ことはでき*ますが、インストールの複雑さが増すため、*お勧めできません*。 プールレベルでこれらのコマンドを実行することによって、プールにすべてのロールが含まれていない場合 (たとえば、Web サービスがない場合)、設定はレジストラーの役割に対してのみ設定されます。 その場合、Web サービスはグローバルレベルの設定を使用して実行されます。これにより、混乱を招く可能性があります (特に、意図せずに実行された場合)。

クライアントが1つのプールのレジストラー設定と別のプールの Web サービス設定を使用していて、認証設定が不整合な状態にある場合は、yous クライアントでログオンできないことがあります。

また、プールに対して1つの役割しか存在しない場合は、次の操作も行います。 
* Set-存在するロールに対応する設定のみを設定します。 一部の設定が設定*されてい*ないため、特別な警告は表示されません。 
* Get-存在するロールに対応する設定と、存在しないロールのグローバル設定が返されます。
* プールのどちらのロールも存在しない場合、Set と Get の両方が、エラーメッセージを返します。
* プールの両方の役割が存在するが、ポリシーがプールレベルで定義されていない場合は、Get-エラーメッセージが返されます。

これらの値に対して wisest を実行し、変更を行う前に、スクリーンショットを表示したり、開始状態を記録したりすることができます。 また、変更履歴を OneNote に保存することも検討してください。

> [!NOTE]
> 
> 注: CsAuthConfig を構成した後、設定を有効にするには、各コンピューターで [CsComputer を有効にする] を実行する必要があります。

> [!IMPORTANT]
> Lync Web Access (LWA) を使用していて、外部アクセスにフォームベースのアクセス (FBA) を使用する必要がある場合は、これらのシナリオをサポートするために、クライアントが匿名アクセスでアクセスできるように LWA を再構成してください。 同様に、ダイヤルイン Pin を使用している場合、FBA は外部ユーザーに対してのみブロックされます。 Pin を変更する必要がある場合は、社内にログインしてください。

> [!NOTE]
> 
> ブロックされた外部パラメーターを使用して NTLM をブロックする場合は、SIP チャネルの内部で NTLM がブロックされることに注意してください。 ただし、2010よりも新しい Skype for Business および Lync クライアントは、ログイン時に HTTP 経由でのサインインを使用するため、内部的にログインしてから、SIP 経由でログインする証明書を取得するため、ログインできます。 ただし、2010より古いクライアントは、この状況では内部ではログインできません。また、ユーザーがセキュリティで保護された機能を再開できるように、これらのアプリケーションをアップグレードすることをお勧めします。


## <a name="links"></a>リンク 
- PowerShell に関するその他の情報:
    -  [CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [Set-CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/set-csauthconfig?view=skype-ps)

- コマンドの使用方法や、インストールに必要な CU の詳細については、次の手順に従います。
    - [コマンドレットのブリーフィング](https://support.microsoft.com/en-us/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - [Skype For Business Server 2015 の更新プログラム](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)(全般)
    - [2018 年7月の Skype For Business Server 2015、コアコンポーネント CU](https://support.microsoft.com/en-us/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) (6.0.9319.534)


 
