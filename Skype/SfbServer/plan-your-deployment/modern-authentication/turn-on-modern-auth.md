---
title: ネットワークの内部および外部で従来の認証方法をオフにする計画
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: この記事では、管理者が企業の内部および外部で使用される認証方法を詳細に制御できるコマンドレットの概要を示します。 管理者は、認証方法を内部または外部のネットワークで有効またはオフにできます。
ms.openlocfilehash: dca7dca332564442110c626a222f7ed5d138efaf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810030"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a>ネットワークの内部および外部で従来の認証方法をオフにする計画。

> [!NOTE]
> この記事を読もうとする場合は、サポートされている最新の認証トポロジ、ADAL、およびモダン認証構成について既に知っている必要がありますが、ない場合は、開始する必要がある記事を次に示します。 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal)
  
モダン認証は、Two-Factor 認証や証明書ベースの認証など、より安全な認証方法を有効にしているばかりでなく、ユーザー名やパスワードを必要とせずにユーザーの承認を実行できます。 非常に便利です。

この記事では、Skype for Business Servers に対するサービス拒否 (DOS) 攻撃で悪用された穴を、認証に使用される以前の方法 (外部、内部、または両方) をネットワークにオフにすることで、接続に役立ちます。 たとえば、DOS 攻撃を停止するのに役立つ 1 つの良い方法は、Windows 統合認証 (NTLM と Kerberos を含む) をオフにすることです。 NTLM を外部でオフにし、証明書ベースの認証に依存すると、パスワードが露出から保護されます。 これは、NTLM はパスワード資格情報を使用してユーザーを認証しますが、証明書ベースの認証 (最新の認証によって有効になっている) は認証を行わないためです。 つまり、DOS 攻撃を削減する理想的なオプションの 1 つは、NTLM を外部からブロックし、代わりに証明書ベースの認証のみを使用する方法です。

よし、始めましょう。

## <a name="what-would-you-be-changing"></a>何を変更しますか? 

これらのコマンドレットは、SIP と Web サービスの両方のアクセス ポイントで機能します。 これら 2 つのチャネルでは異なるアクセス方法を使用しますが、NTLM と Kerberos から匿名アクセスへのゲームを実行しますが、Skype for Business で使用される標準的な方法はすべて考慮されています。

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a>Get-and Set-CsAuthConfig コマンドレットを取得する方法

これらのコマンドレットは、Microsoft Skype for Business Server 2015 の 2018 年 7 月の累積的な更新プログラム (6.0.9319.534) 以降にのみインストールされ、Skype for Business サーバー用に展開できるさまざまなトポロジがあります。

## <a name="topologies"></a>トポロジ

これらのトポロジは、このシナリオに関連するサポートされるトポロジです。 たとえば、メソッドのブロックに関するサポートにアクセスする必要がある場合は、次の種類の構成が必要になります。 

> [!IMPORTANT]
> 以下の表と説明では、モダン認証は MA と省略され *、Windows 統合* 認証は Win と省略 __されます__。 Windows 統合認証は、NTLM 認証と Kerberos 認証の 2 つの方法で構成されています。 テーブルを正しく読み取るには、これを知る必要があります。


|       |外部  |内部的  |パラメーター  |
|---------|:---------|:---------|---------|
|__種類 1__   |  MA + Win       | MA + Win         |  AllowAllExternallyAndInternally       |
|__種類 2__   |  MA       | MA + Win         | BlockWindowsAuthExternally        |
|__種類 3__   |  MA       | MA        | BlockWindowsAuthExternallyAndInternally        |
|__種類 4__   |  MA       | Win        | BlockWindowsAuthExternallyAndModernAuthInternally    |
|__種類 5__   |  MA + Win       | Win        | BlockModernAuthInternally         |

__型 1 説明:__ これは、Skype for Business Server でMA __が有効になっている場合の__ 既定のシナリオです。 言い換えると、この設定が構成 *MA* 開始点になります。

__型 2 説明:__ このトポロジは *NTLM* を外部でブロックしますが、NTLM または Kerberos (ADAL をサポートしないクライアントの場合) は内部で *動作できます*。 クライアントが ADAL をサポートしている場合、クライアントは内部MA使用します。

__型 3 説明:__ このトポロジでは、すべてのユーザー MAが必要です。 たとえば、証明書ベースの認証でパスワードの使用をオフにした場合、すべての ADAL 対応クライアントはこのトポロジで機能し、パスワードは利用されません。

__型 4 説明:__ このトポロジは、NTLM を外部的に *ブロック* し、MAブロックします。 すべてのクライアント *が内部で* 従来の認証方法を *使用できます* (ADAL 対応のクライアントでも)。

__型 5 説明:__ 外部では、モダン ADAL クライアントは MA を使用し、ADAL をサポートしないクライアントはレガシ認証方法を使用します。 ただし、*内部的には、**すべてのクライアント* がレガシ認証 (すべての ADAL 対応クライアントを含む) を使用します。

利用可能なオプションでパスワードを保護する目標を見失うのは非常に簡単です。 DOS 攻撃を回避するために、外部で MA (証明書ベースの認証を構成するなど) を使用するのが理想的な状況です。 最新のクライアントに内部で活用する場合は、Skype for Business Server の DOS 攻撃に関するネットワークの将来性も証明できます。

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a>グローバル レベルでSet-CsAuthConfigを使用する理由

この `Set-CsAuthConfig` コマンドレットは、レジストラーロールと Web サービス ロールの両方に構成を影響します。

このコマンドレットは、Skype for Business サーバーのグローバル レベルで実行することを意図しています。 プール *レベル* で実行できますが、インストールが複雑になるので、お勧めできません。 これらのコマンドをプール レベルで実行すると、プールに含まれる役割の一部が存在しない場合 (たとえば、Web サービスが含まれていない場合)、設定はレジストラーの役割にのみ設定されます。 その場合、Web サービスはグローバル レベルの設定を引き続き使用します。これは動作を混乱させる可能性があります (特に、これが意図せずに行われた場合)。

クライアントが 1 つのプールのレジストラー設定を使用し、別のプールの Web サービス設定を使用し、認証設定が矛盾した状態にある場合、クライアントはログオンできない可能性があります。

また、プールに存在する役割が 1 つしか存在しない場合は、次の条件を使用します。 
* Set- は、存在するロールに対応する設定のみを設定します。 一部の設定が設定されていないので、特別な警告 *は表示* されない。 
* Get- は、存在するロールに対応する設定と、存在しないロールのグローバル設定を返します。
* プールに対してどちらの役割も存在しない場合、Set- と Get- の両方がエラー メッセージを返します。
* 両方の役割がプールに存在するが、ポリシーがプール レベルで定義されていない場合、Get- はエラー メッセージを返します。

これらの値に対して Get- を実行し、変更を加える前に開始状態をスクリーンショットまたは記録した方が最も便利な場合があります。 OneNote で変更のログを保持する方法も検討してください。

> [!NOTE]
> 
> 注: CsAuthConfig を構成した後、設定を有効Enable-CsComputerコンピューターごとにこのコマンドを実行する必要があります。

> [!IMPORTANT]
> Lync Web Access (LWA) を使用し、外部アクセスにフォーム ベース アクセス (FBA) を使用する必要がある場合は、クライアントが匿名アクセスでアクセスしてこれらのシナリオをサポートできるよう LWA を再構成します。 同様に、ダイヤルイン Pin を使用する場合、FBA は外部ユーザーに対してだけブロックされます。 Pin を変更する必要がある場合は、社内で企業にログインする必要があります。

> [!NOTE]
> 
> BlockWindowsAuthExternally パラメーターを使用して NTLM を外部的にブロックする場合は、SIP チャネルの NTLM が内部的にブロックされる点にも注意してください。 ただし、2010 より新しい Skype for Business クライアントおよび Lync クライアントは、サインインに NTLM over HTTP を使用し、内部的にログインしてから、SIP 経由でログインする証明書をフェッチする場合に、引き続きログインできます。 ただし、2010 年を超えるクライアントはこの状況では内部ログインを行えなくないので、ユーザーが安全な機能を再開できるよう、これらのアプリケーションのアップグレードを検討する必要がある場合があります。

> [!IMPORTANT] 
> Skype for Business Web アプリケーションの中には、この機能をサポートMA。 そのため、BlockWindowsAuthExternallyAndInternally シナリオを使用すると、これらのアプリケーションにアクセスできません。 サポートMA使用しないアプリケーションは、Web スケジューラ、ダイヤルイン ページ、Skype for Business コントロール パネル (CSCP)、および応答グループ設定ページです。 

## <a name="links"></a>リンク 
- PowerShell の詳細については、次の情報を参照してください。
    -  [Get-CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [Set-CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/set-csauthconfig?view=skype-ps)

- コマンドの使い方や、コマンドのインストールに必要な CU について詳しくは、次の手順をご覧ください。
    - [コマンドレット の説明](https://support.microsoft.com/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - [Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015) の更新プログラム (全般)
    - [2018 年 7 月 Skype for Business Server 2015](https://support.microsoft.com/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server)コア コンポーネント CU (6.0.9319.534)


 
