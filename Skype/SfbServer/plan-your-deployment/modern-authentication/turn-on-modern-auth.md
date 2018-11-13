---
title: ネットワークに内部と外部を従来の認証方法をオフにしようとしています。
ms.author: tracyp
author: MSFTTracyP
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: ''
description: 認証方法の詳細に制御を管理者に提供するこの資料のアウトライン コマンドレットでは、業務上の内側と外側を使用します。 管理者は、認証方法を有効にまたは内部、または外部のネットワークにします。
ms.openlocfilehash: 51dfaf9dc4c65afdd615cf29632c21d4cba08f65
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2018
ms.locfileid: "26294847"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a>無効にする従来の認証方法内部と外部のネットワークを計画しています。

> [!NOTE]
> この資料を参照しようとする場合は、既に、現代の認証のサポートされているトポロジ、ADAL を知っておく必要があり、最新の認証の構成についてですが、ない場合にここでは、を開始する必要がある記事。 
>  + [https://docs.microsoft.com/en-us/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](https://docs.microsoft.com/en-us/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
>  + [https://docs.microsoft.com/en-us/skypeforbusiness/manage/authentication/use-adal](https://docs.microsoft.com/en-us/skypeforbusiness/manage/authentication/use-adal)
  
現代の認証が有効にする二要素認証、または証明書ベースの認証などの認証方法をより安全なすぎる、ユーザー名またはパスワードを必要とせず、ユーザーの承認を伝送可能です。 非常に便利です。

この資料に役立つビジネス サーバーは、古いメソッドの外部で、内部的には、認証の使用をオフにしても、ネットワークへの Skype のサービス拒否 (DOS) 攻撃に悪用されたことをプラグの穴です。 たとえば、DOS 攻撃を防止するための 1 つの良い方法は、Windows 統合認証 (NTLM および Kerberos が含まれています) を無効にするでしょう。 外部の NTLM を無効にして、証明書ベースの認証に依存することは、パスワードの漏えいを防ぐに役立ちます。 これは、NTLM パスワード資格情報を使用してユーザーを認証する証明書ベースの認証 - - 現代の認証が有効になっていないためです。 DOS 攻撃を軽減することを意味 1 つの理想的なオプション、外部では、NTLM をブロックし、証明書ベースの唯一の認証の使用が、代わりにします。

さあ、始めましょう。

## <a name="what-would-you-be-changing"></a>何を頻繁に変更されるでしょうか。 

SIP および Web サービスのアクセス ポイントには、これらのコマンドレットが動作します。 これら 2 つのチャネルを使用して、匿名アクセスは、NTLM と Kerberos の色域を実行して、異なるアクセス方法がビジネスのため、Skype で使用されるすべての標準的な方法を講じてを考慮します。

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a>Get とセットで CsAuthConfig コマンドレットを取得する方法

これらのコマンドレットをインストールするだけ、2018年 7 月累積的な (6.0.9319.534) 用の更新プログラム Microsoft Skype ビジネス サーバー 2015 年を転記し、さまざまなビジネス サーバーは、Skype のロールアウトされることがあるトポロジがある場合、します。

## <a name="topologies"></a>トポロジ

ことが重要ではサポートされているトポロジがこのシナリオに関係することに留意してください! メソッドのブロックとヘルプのサポートにアクセスする場合は、以下のタイプの間で構成を使用する必要があります。 

> [!IMPORTANT]
> 表および下記の説明では、 __MA__と*最新の認証*は省略されてし、__勝利__として*Windows 統合認証*が簡略化されました。 目印として Windows 統合認証で構成された 2 つの方法: NTLM と Kerberos 認証です。 このテーブルを正しく読み取ることを確認する必要があります。


|       |外部から  |内部的に  |パラメーター  |
|---------|:---------|:---------|---------|
|__タイプ 1__   |  MA + 勝利       | MA + 勝利         |  AllowAllExternallyAndInternally       |
|__タイプ 2__   |  MA       | MA + 勝利         | BlockWindowsAuthExternally        |
|__タイプ 3__   |  MA       | MA        | BlockWindowsAuthExternallyAndInternally        |
|__タイプ 4__   |  MA       | 勝利        | BlockWindowsAuthExternallyAndModernAuthInternally    |
|__タイプ 5__   |  MA + 勝利       | 勝利        | BlockModernAuthInternally         |

__1 の説明を入力:__ 既定値は、この__シナリオの MA がオンになって Skype のビジネス サーバーの__です。 つまり、これは、*開始点*の MA が構成されている場合。

__タイプ 2 の説明:__ このトポロジ NTLM*外部*ブロックですが、NTLM または Kerberos (ADAL をサポートしていないクライアント) が*内部で*動作します。 ADAL をクライアントがサポートしている場合 MA を内部的に使用します。

__タイプ 3 の説明:__ このトポロジでは、すべてのユーザーの MA が必要です。 ADAL 対応のすべてのクライアントは、このトポロジで動作し、Auth. の証明書ベースのパスワードの使用を無効にするなどの場合は、パスワードは利用できません。

__タイプ 4 の説明:__ このトポロジは、NTLM*外部*と MA を内部でブロックします。 により、従来の認証メソッド*内部で*(ADAL に対応したクライアント) を使用する*すべてのクライアント*ができます。

__タイプ 5 の説明:__ 現代 ADAL クライアントが MA を使用して*外部から*、および ADAL をサポートしていないすべてのクライアントは従来の認証方法を使用します。 (すべての ADAL に対応したクライアントを含む) 従来の認証を使用する*すべてのクライアント*では*内部的に*します。

使用可能なオプションでパスワードを保護する目的を見失うことに非常に簡単です。 留意する理想的な状態では、DOS 攻撃を回避するのには (たとえばを構成する証明書ベース認証)、MA の外部を使用します。 将来の学習を使用する場合、内部的には、最近のクライアント、Skype に関するビジネス サーバー DOS 攻撃をネットワークします。

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a>グローバル レベルで設定 CsAuthConfig を使用する理由

`Set-CsAuthConfig` 、レジストラーと Web サービスの役割の両方でコマンドレットの効果の構成です。

このコマンドレットは、ビジネスのサーバーに、Skype のグローバル レベルで実行するものです。 これは、複雑さのインストールに追加されますので、プールのレベルは*お勧めできません*で実行*できます*。 プールはすべてのロールが含まれていない場合は、プール レベルでは、これらのコマンドを実行する (たとえば、ことがない Web サービス)、レジストラーの役割の設定にのみ設定されます。 場合は、Web サービスはこの方向で (特にこれは意図しない) 場合は、混乱を招く動作をすることができます、グローバルなレベルから設定します。

クライアントが別のプールから 1 つのプールからレジストラーの設定と Web サービスを使用し、認証の設定が矛盾した状態では、yous クライアントできないことがありますにログオンします。

また、プールの 1 つのロールがある場合。 
* セットは、のみに存在する役割に対応する設定を設定します。 いくつかの設定が設定*されていない*ために、特別な警告は表示されません。 
* Get が存在する場合、役割に対応する設定され、存在しないロール用のグローバル設定を返します。
* どちらのロールがプールに存在する場合は、両方セットと Get ではエラー メッセージを返します。
* プールの両方のロールは、プール レベルのポリシーが定義されていない場合は、Get はエラー メッセージを返します。

賢いか、取得 - これらの値と、スクリーン ショットを変更する前に、開始時の状態を記録する場合があります。 OneNote での変更のログを保持することも検討する可能性があります。

> [!IMPORTANT]
> Lync Web アクセス (LWA) を使用するいるし、外部からのアクセスのフォーム ベースのアクセス (FBA) を使用する必要があります、クライアントを使用するとこれらのシナリオをサポートするために匿名アクセスでアクセスできるように、LWA を再構成します。 同様に、暗証番号 (pin) では、ダイヤルインを使用する場合、外部ユーザーにのみ FBA がブロックされます。 自分の pin を変更する必要がある場合は、ログインを行うためには、内部的には、企業を対象にする必要があります。

## <a name="links"></a>リンク ##
- PowerShell の詳細については。
    - Get CsAuthConfig[https://github.com/MicrosoftDocs/office-docs-powershell/blob/master/skype/skype-ps/skype/Get-CsAuthConfig.md](https://github.com/MicrosoftDocs/office-docs-powershell/blob/master/skype/skype-ps/skype/Get-CsAuthConfig.md)
    - セット CsAuthConfig[https://github.com/MicrosoftDocs/office-docs-powershell/blob/master/skype/skype-ps/skype/Set-CsAuthConfig.md](https://github.com/MicrosoftDocs/office-docs-powershell/blob/master/skype/skype-ps/skype/Set-CsAuthConfig.md)

- 方向を指定または CU 上のコマンドを使用する方法の詳細は、それらをインストールするのには必要です。
    - コマンドレットのブリーフィング[https://support.microsoft.com/en-us/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication](https://support.microsoft.com/en-us/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - ビジネス サーバー 2015 (全般) の Skype 用の更新プログラム[https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)
    - ビジネス サーバー 2015 年 2018年 7 月 Skype のコア コンポーネント CU (6.0.9319.534)[https://support.microsoft.com/en-us/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server](https://support.microsoft.com/en-us/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server)


 