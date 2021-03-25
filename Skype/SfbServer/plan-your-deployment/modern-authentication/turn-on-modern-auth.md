---
title: ネットワークに対してレガシ認証方法を内部および外部でオフにする計画
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
description: この記事では、管理者がビジネスの内部および外部で使用される認証方法の制御を管理者に提供するコマンドレットの概要を説明します。 管理者は、認証方法を内部的または外部的にネットワークに対してオンまたはオフにできます。
ms.openlocfilehash: 3d7217167f7e72c4db0ec438fb20d746cd612cc2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116055"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a>従来の認証方法をネットワークに対して内部および外部でオフにする計画。

> [!NOTE]
> この記事を読む場合は、サポートされているモダン認証トポロジ、ADAL、およびモダン認証の構成について既に知っている必要がありますが、そうしない場合は、開始する必要がある記事を次に示します。 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](./topologies-supported.md)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](/skypeforbusiness/manage/authentication/use-adal)
  
最新の認証では、Two-Factor Auth や証明書ベースの認証など、より安全な認証方法を有効にできるので、ユーザー名やパスワードを必要とせずにユーザーの承認を実行できます。 これは非常に便利です。

この記事では、Skype for Business Servers でサービス拒否 (DOS) 攻撃で悪用された穴を、認証、外部、内部、または両方で使用される古い方法をネットワークにオフにすることで、プラグインするのに役立ちます。 たとえば、DOS 攻撃を停止するのに役立つ方法の 1 つは、Windows 統合認証 (NTLM と Kerberos を含む) をオフにすることです。 NTLM を外部でオフにし、証明書ベースの認証に依存すると、パスワードが露出から保護されます。 これは、NTLM がパスワード資格情報を使用してユーザーを認証するが、証明書ベースの認証 (モダン認証で有効) が有効になっていないためです。 つまり、DOS 攻撃を減らす理想的な方法の 1 つは、NTLM を外部でブロックし、代わりに証明書ベースの認証のみを使用する方法です。

よし、始めましょう。

## <a name="what-would-you-be-changing"></a>何を変更しますか? 

これらのコマンドレットは、SIP と Web サービスの両方のアクセス ポイントで機能します。 これら 2 つのチャネルは、NTLM と Kerberos から匿名アクセスまでの色域を実行する異なるアクセス方法を使用しますが、Skype for Business で使用される標準メソッドはすべて考慮されています。

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a>Get-and Set-CsAuthConfigコマンドレットを取得する方法

これらのコマンドレットは、Microsoft Skype for Business Server 2015 の 2018 年 7 月の累積的な更新プログラム (6.0.9319.534) 以降にのみインストールされ、Skype for Business サーバー用に展開できるさまざまなトポロジがあります。

## <a name="topologies"></a>トポロジ

これらのトポロジは、このシナリオに関連するサポートされているトポロジです。 たとえば、メソッドのブロックに関するヘルプのサポートに移動する必要がある場合は、以下の種類の間で構成する必要があります。 

> [!IMPORTANT]
> 以下の表と説明では、モダン認証は"Windows 統合認証"と省略されMA *Windows 統合* 認証は Win と省略 __されます__。 Windows 統合認証は、NTLM 認証と Kerberos 認証の 2 つの方法で構成されています。 テーブルを正しく読み取るには、これを知る必要があります。


|       |外部的  |内部的に  |パラメーター  |
|---------|:---------|:---------|---------|
|__タイプ 1__   |  MA + Win       | MA + Win         |  AllowAllExternallyAndInternally       |
|__タイプ 2__   |  MA       | MA + Win         | BlockWindowsAuthExternally        |
|__タイプ 3__   |  MA       | MA        | BlockWindowsAuthExternallyAndInternally        |
|__タイプ 4__   |  MA       | Win        | BlockWindowsAuthExternallyAndModernAuthInternally    |
|__タイプ 5__   |  MA + Win       | Win        | BlockModernAuthInternally         |

__タイプ 1 Description:__ これは、Skype for Business Server のMAが __有効になっている場合__ の既定のシナリオです。 つまり、この設定が構成されている場合のMAです。

__タイプ 2 Description:__ このトポロジは *NTLM* を外部でブロックしますが、NTLM または Kerberos (ADAL をサポートしないクライアントの場合) は内部的に *動作します*。 クライアントが ADAL をサポートしている場合は、内部MA使用します。

__タイプ 3 Description:__ このトポロジでは、すべてのユーザー MAを使用する必要があります。 ADAL 対応のすべてのクライアントは、このトポロジで動作し、たとえば、証明書ベースの Auth でパスワードの使用をオフにした場合、パスワードは活用されません。

__タイプ 4 Description:__ このトポロジでは、NTLM が外部で *ブロックされ* 、MAブロックされます。 これにより、 *すべてのクライアントが* 内部で従来の認証 *方法を使用* できます (ADAL 対応のクライアントでも)。

__タイプ 5 説明:__ *外部* では、モダン ADAL クライアントは MA を使用し、ADAL をサポートしないクライアントはレガシ認証方法を使用します。 ただし、*内部的には、**すべてのクライアント* がレガシ認証 (すべての ADAL 対応クライアントを含む) を使用します。

利用可能なオプションでパスワードを保護する目的を見失うのはかなり簡単です。 DOS 攻撃を回避するには、外部MA (たとえば、証明書ベースの認証を構成する) を使用するのが理想的な状況です。 最新のクライアントに対して内部的に活用する場合は、Skype for Business Server DOS 攻撃に関するネットワークの将来性も確認できます。

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a>グローバル レベルでSet-CsAuthConfigを使用する理由

コマンドレット `Set-CsAuthConfig` は、レジストラーと Web サービスの両方の役割に対して構成を影響します。

このコマンドレットは、Skype for Business サーバーのグローバル レベルで実行することを意図しています。 プール *レベル* で実行できますが、インストールに複雑さを加えるので、お勧めしません。 これらのコマンドをプール レベルで実行すると、プールに含まれるすべての役割 (Web サービスが含まれていないなど) が存在しない場合、設定はレジストラー ロールにのみ設定されます。 その場合、Web サービスはグローバル レベルの設定を続けます。これは動作が混乱する可能性があります (特にこれが意図せずに行われた場合)。

クライアントが 1 つのプールのレジストラー設定を使用し、別のプールの Web サービス設定と認証設定が一貫性のない状態にある場合、クライアントはログオンできない可能性があります。

また、プールに存在する役割が 1 つのみである場合は、次の条件を使用します。 
* Set- は、存在する役割に対応する設定のみを設定します。 一部の設定が設定されていないので、特別な警告 *は表示* されない。 
* Get- は、存在する役割に対応する設定と、存在しない役割のグローバル設定を返します。
* プールに対してどちらの役割も存在しない場合、Set と Get- の両方がエラー メッセージを返します。
* 両方の役割がプールに存在するが、ポリシーがプール レベルで定義されていない場合、Get- はエラー メッセージを返します。

これらの値に対して Get- を実行し、変更を加える前に開始状態をスクリーンショットまたは記録する方が最も便利な場合があります。 OneNote で変更のログを保持する場合も検討できます。

> [!NOTE]
> 
> 注: CsAuthConfig を構成した後で、設定を有効Enable-CsComputerコンピューター上で実行する必要があります。

> [!IMPORTANT]
> Lync Web Access (LWA) を使用し、外部アクセスにフォーム ベース アクセス (FBA) を使用する必要がある場合は、クライアントが匿名アクセスを使用してアクセスしてこれらのシナリオをサポートできるよう、LWA を再構成します。 同様に、ダイヤルインピンを使用する場合、FBA は外部ユーザーにのみブロックされます。 ピンを変更する必要がある場合は、社内で会社にログインする必要があります。

> [!NOTE]
> 
> BlockWindowsAuthExternally パラメーターを使用して NTLM を外部的にブロックする場合は、SIP チャネルの NTLM も内部的にブロックされます。 ただし、2010 より新しい Skype for Business クライアントと Lync クライアントは、サインイン、内部的に HTTP 経由で NTLM を使用し、SIP 経由でログインする証明書をフェッチするために、引き続きログインできます。 ただし、2010 より前のクライアントは、この状況では内部的にログインできないので、ユーザーがセキュリティで保護された機能を再開できるよう、これらのアプリケーションのアップグレードを検討する必要があります。

> [!IMPORTANT] 
> Skype for Business Web アプリケーションの中には、このアプリケーションをサポートMA。 したがって、BlockWindowsAuthExternallyAndInternally シナリオを使用すると、これらのアプリケーションにアクセスできません。 サポートをMAアプリケーションは、Web スケジューラ、ダイヤルイン ページ、Skype for Business コントロール パネル (CSCP)、および応答グループ設定ページです。 

## <a name="links"></a>リンク 
- PowerShell の詳細については、次の情報を参照してください。
    -  [Get-CsAuthConfig](/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [Set-CsAuthConfig](/powershell/module/skype/set-csauthconfig?view=skype-ps)

- コマンドの使用方法、またはコマンドのインストールに必要な CU の詳細については、次の手順を実行します。
    - [コマンドレットのブリーフィング](https://support.microsoft.com/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - [Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015) の更新プログラム (全般)
    - [2018 年 7 月 Skype for Business Server 2015 Core Components CU](https://support.microsoft.com/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) (6.0.9319.534)


