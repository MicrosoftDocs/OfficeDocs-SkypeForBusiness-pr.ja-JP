---
title: レガシ認証方法をネットワークの内部および外部にオフにするための計画
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
description: この記事では、ビジネスの内部および外部で使用される認証方法を管理者が制御できるようにするコマンドレットの概要を説明します。 管理者は、内部または外部のネットワークに対して認証方法を有効または無効にすることができます。
ms.openlocfilehash: e2f9a8c9c8576c07de3158fb2446cb3cb89bac72
ms.sourcegitcommit: aae3eeb4dedd825ab176abe7e1aff9463c88799b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "46797455"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a>従来の認証方法をネットワークの内部および外部にオフにする計画を立てます。

> [!NOTE]
> この記事を読むには、サポートされている先進認証トポロジ、ADAL、およびモダン認証構成について既に理解している必要がありますが、それ以外の場合は、次の記事を開始する必要があります。 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal)
  
先進認証では、2要素認証、証明書ベースの認証など、より安全な認証方法を有効にすることはできません。ユーザー名やパスワードを必要とせずにユーザーの認証を実行することができます。 とても便利です。

この記事では、Skype for Business Server でのサービス拒否 (DOS) 攻撃に悪用された可能性のある、認証のために、外部、内部、またはその両方がネットワークに対して使用される以前の方法をオフにすることによって、この問題に対処する方法を説明します。 たとえば、DOS 攻撃を阻止するための適切な方法の1つとして、Windows 統合認証 (NTLM と Kerberos を含む) がオフになっていることがあります。 NTLM を外部で無効にし、証明書ベースの認証を使用すると、パスワードが危険から保護されます。 これは、NTLM がパスワード資格情報を使用してユーザーを認証するのに対して、証明書ベースの認証はモダン認証で有効になっていないためです。 これは、DOS 攻撃を減らすための理想的なオプションの1つとして、NTLM を外部でブロックし、代わりに証明書ベースの認証を使用することを意味します。

そのため、始めましょう。

## <a name="what-would-you-be-changing"></a>何を変更しますか? 

これらのコマンドレットは、SIP と Web サービスのアクセスポイントの両方で機能します。 これらの2つのチャネルは、さまざまなアクセス方法を使用していますが、NTLM と Kerberos から匿名アクセスへの域を使用しているため、Skype for Business で使用される標準的な方法はすべて考慮されています。

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a>Get および Set-CsAuthConfig コマンドレットを取得する方法

これらのコマンドレットは、Microsoft Skype for Business Server 2015 の2018年7月の累積的な更新プログラム (6.0.9319.534) に対してのみインストールされます。その後、さまざまなトポロジを使用して Skype for business server にロールアウトすることができます。

## <a name="topologies"></a>テクノロジ

このシナリオでは、これらがサポートされているトポロジであることに留意することが重要です。 たとえば、メソッドのブロックに関するヘルプをサポートする必要がある場合は、以下の種類の構成が必要になります。 

> [!IMPORTANT]
> 下の表と説明では、 *モダン認証* は __MA__ として短縮され、 *Windows 統合認証* は __Win__という略語に短縮されています。 事前通知として、Windows 統合認証は、NTLM 認証と Kerberos 認証の2つの方法で構成されます。 テーブルを正しく読み取るには、このことを理解しておく必要があります。


|       |から  |内部的  |パラメーター  |
|---------|:---------|:---------|---------|
|__種類1__   |  MA + Win       | MA + Win         |  AllowAllExternallyAndInternally       |
|__種類2__   |  概要       | MA + Win         | BlockWindowsAuthExternally        |
|__種類3__   |  概要       | 概要        | BlockWindowsAuthExternallyAndInternally        |
|__種類4__   |  概要       | 差し上げ        | BlockWindowsAuthExternallyAndModernAuthInternally    |
|__種類5__   |  MA + Win       | 差し上げ        | BlockModernAuthInternally         |

__「1」と入力します。__ これは、MA が Skype for Business Server __でオンに__ なっている場合の既定のシナリオです。 言い換えると、これは MA が構成されている *開始点* です。

__種類2の説明:__ このトポロジでは、NTLM が *外部*でブロックされますが、(ADAL をサポートしていないクライアントの) *内部*での ntlm または Kerberos を使用できます。 クライアントが ADAL をサポートしている場合は、MA を内部で使用します。

__種類 3: 説明:__ このトポロジでは、すべてのユーザーに MA が必要です。 すべての ADAL 対応クライアントはこのトポロジで動作し、たとえば、証明書ベースの認証でパスワードの使用を無効にした場合には、パスワードは利用されません。

__種類4の説明:__ このトポロジでは、内部的に NTLM が *外部* および MA にブロックされます。 これにより、 *すべてのクライアント* が *内部* (ADAL 対応クライアントでも) 従来の認証方法を使用できるようになります。

__種類5の説明:__ *外部*では、モダン adal クライアントは MA を使用し、adal をサポートしていないクライアントは従来の認証方法を使用します。 しかし、 *内部的*に *すべてのクライアント* が従来の認証を使用します (すべての ADAL 対応クライアントを含む)。

使用可能なオプションで、パスワードを保護する目的を、非常に簡単に追跡できます。 理想的な状況は、(証明書ベースの認証を構成するなど) 外部の MA を使用して、DOS 攻撃を回避することです。 モダンクライアントに対して内部でこのサービスを利用している場合は、Skype for Business Server の DOS 攻撃に関するネットワークの未来を証明することもできます。

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a>グローバルレベルで設定-CsAuthConfig を使用する理由

この `Set-CsAuthConfig` コマンドレットは、レジストラーと Web サービスの役割の両方についての構成に影響します。

このコマンドレットは、Skype for Business server のグローバルレベルで実行することを目的としています。 プールレベルで実行 *でき* ますが、これは推奨され *ません* 。これにより、インストールが複雑になります。 プールレベルでこれらのコマンドを実行することにより、プールに含まれているすべての役割 (たとえば、Web サービスがない場合) について、設定はレジストラーの役割に対してのみ設定されます。 その場合、Web サービスはグローバルレベルの設定を使用して実行されます。これは、混乱を招く可能性があります (特に意図的に実行されていない場合)。

クライアントが1つのプールのレジストラー設定を使用し、別のプールから Web サービス設定を使用していて、認証設定が不整合な状態にある場合、yous クライアントはログオンできないことがあります。

また、プールに存在する役割が1つだけの場合は、次のようになります。 
* Set-は、存在する役割に対応する設定のみを設定します。 一部の設定が設定 *されていない* ため、特別な警告は表示されません。 
* Get-は存在するロールに対応する設定を返し、存在しないロールのグローバル設定を返します。
* プールに対してどちらの役割も存在しない場合は、Set と Get の両方がエラーメッセージを返します。
* プールに両方の役割が存在していても、ポリシーがプールレベルで定義されていない場合、Get はエラーメッセージを返します。

Wisest は、これらの値に対して Get を実行し、変更を行う前にスクリーンショットを作成したり、開始状態を記録したりすることができます。 また、変更のログを OneNote に保存することも検討してください。

> [!NOTE]
> 
> 注: CsAuthConfig を構成した後、設定を有効にするために、各コンピューターで [CsComputer] を実行する必要があります。

> [!IMPORTANT]
> Lync Web Access (LWA) を使用していて、外部アクセスに対してフォームベースのアクセス (FBA) を使用する必要がある場合は、これらのシナリオをサポートするためにクライアントが匿名アクセスでアクセスできるように LWA を再構成します。 同様に、ダイヤルイン Pin を使用した場合、FBA は外部ユーザーに対してのみブロックされます。 Pin を変更する必要がある場合は、社内で実行するために会社にログインする必要があります。

> [!NOTE]
> 
> BlockWindowsAuthExternally パラメーターを使用して、NTLM を外部でブロックする場合は、SIP チャネルに対して内部的に NTLM がブロックされることに注意してください。 ただし、2010より新しい Skype for Business および Lync クライアントは、内部的には、ログインに対して NTLM over HTTP を使用してから、SIP 経由でログインする証明書を取得するため、引き続きログインすることができます。 ただし、2010より前のクライアントは、このような状況では内部でログインできないため、ユーザーがセキュリティで保護された機能を再開できるように、これらのアプリケーションをアップグレードすることをお勧めします。

> [!IMPORTANT] 
> 一部の Skype for Business web アプリケーションは MA をサポートしていません。 そのため、BlockWindowsAuthExternallyAndInternally のシナリオを使用すると、これらのアプリケーションにアクセスすることはできません。 MA をサポートしていないアプリケーションとしては、Web スケジューラ、ダイヤルインページ、Skype for Business コントロールパネル (CSCP)、応答グループの設定ページがあります。 

## <a name="links"></a>Links 
- 詳細については、以下を参照してください。
    -  [取得-CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [設定-CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/set-csauthconfig?view=skype-ps)

- コマンドを使用する方法、またはそれらをインストールするために必要な CU の詳細については、以下を参照してください。
    - [コマンドレットのブリーフィング](https://support.microsoft.com/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - [Skype For Business Server 2015 の更新プログラム](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015) (全般)
    - [2018 年7月の Skype For Business Server 2015、コアコンポーネント CU](https://support.microsoft.com/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) (6.0.9319.534)


 
