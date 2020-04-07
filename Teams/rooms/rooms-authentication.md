---
title: Microsoft Teams のルームでの認証
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-collaboration
description: Microsoft Teams ルームの先進認証の構成方法について説明します
ms.openlocfilehash: bef547ab0b9ade2edc433ec64bb1ef61eee4c040
ms.sourcegitcommit: 0fdc60840f45ff5b0a39a8ec4a21138f6cab49c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/07/2020
ms.locfileid: "43160114"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>Microsoft Teams のルームでの認証

Microsoft Teams 会議室デバイスのアカウント管理は、アプリケーションレベルで処理されます。 アプリケーションは、Microsoft Teams、Skype for Business、Exchange に接続して、room アカウントのリソースを取得して、通話と会議のエクスペリエンスを有効にします。 このデバイスは、常に機能するための限定されたものであり、通話プランを使って構成されているデバイスの場合は、そのデバイスに実装されているカスタムロックダウンメカニズムを使うことができます。 これは、これらのデバイスの認証は、エンドユーザーのデバイスとは異なる方法で行われることを意味します。  

Microsoft Teams 室のデバイスを Office 365 で使用しているすべてのユーザーは、モダン認証をお勧めします。 Exchange server または Skype for Business server のオンプレミス展開を使用している場合は、先進認証を有効にするために Azure Active Directory (Azure AD) との[ハイブリッド先進認証](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview)を構成します。

先進認証は、Microsoft Teams の会議室バージョン4.4.25.0 以降でサポートされています。

## <a name="modern-authentication"></a>先進認証

Microsoft Teams の会議室のアプリケーションで先進認証を使用する場合、Microsoft Teams、Exchange、Skype for Business への接続に Active Directory Authentication Library (ADAL) が使用されます。 Microsoft Teams のルームデバイスは共有デバイスであり、夜間の再起動を実行して、スムーズに機能し、重要なオペレーティングシステム、ドライバー、ファームウェア、またはアプリケーションの更新プログラムを入手します。 先進認証メカニズムでは、OAuth 2.0 での[リソース所有者のパスワード資格情報](https://tools.ietf.org/html/rfc6749#section-1.3.3)の許可の種類を使用します。これには、ユーザーの操作は必要ありません。 これは、Microsoft Teams のルームアプリケーションで使用されるユーザーアカウントとリソースアカウントの先進認証のしくみとの主な違いの1つです。 このため、Microsoft Teams の会議リソースアカウントは、多要素認証 (MFA)、スマートカード認証、またはクライアント証明書ベースの認証を使用するように構成しないでください (すべてのエンドユーザーが使用可能)。

Microsoft Teams の会議室のデバイスとエンドユーザーのデバイスでの先進認証の動作の主な違いは、リソースアカウントを使用して、"デバイスに対して苦情としてマークする"、"ハイブリッド Azure AD に参加しているデバイスを要求する" などのデバイスレベルの条件付きアクセスポリシーを適用することはできません。 これは、アプリケーションレベルで使用されている場合、デバイスレベルの概念が先進認証に適用されないためです。 代わりに、[次](https://techcommunity.microsoft.com/t5/intune-customer-success/bg-p/IntuneCustomerSuccess)のガイダンスを使用して、Microsoft Intune にデバイスを登録して、コンプライアンスポリシーを適用することができます。

## <a name="enable-modern-authentication-on-a-microsoft-teams-rooms-device"></a>Microsoft Teams 室のデバイスで先進認証を有効にする

Microsoft Teams のルームで Skype for Business と Exchange の先進認証を使用するには、Microsoft Teams 室のデバイスでの先進認証のクライアント側設定を有効にします。 これは、デバイスの設定または XML 構成ファイルで行うことができます。

> [!NOTE]
> 先進認証のためにクライアント側の設定を有効にする前に、先進認証を使用するように環境が正しく設定されていることを確認してください。

### <a name="using-device-settings"></a>デバイス設定を使用する

1. Microsoft チームルームのデバイスで、[**詳細**(**..**.)] をクリックします。
    
2. [**設定**] を選択し、デバイス管理者のユーザー名とパスワードを入力します。
3. [**アカウント**] タブに移動し、**先進認証**を有効にして、[**保存して終了**] を選択します。

### <a name="using-the-xml-config-file"></a>XML 構成ファイルを使用する

SkypeSettings .xml ファイルで、次のように先進認証 XML 要素を**True**に設定します。

```
<ModernAuthEnabled>True</ModernAuthEnabled>
```

この設定を適用するには、「 [Microsoft Teams のコンソール設定を XML 構成ファイルを使ってリモートで管理](xml-config-file.md)する」を参照してください。

## <a name="prepare-your-environment-for-modern-authentication"></a>先進認証のために環境を準備する

作業を始める前に、Office 365 と Azure AD で使用する id モデルを理解していることを確認してください。 詳細については、「office [365 の id モデルと Azure Active Directory](https://docs.microsoft.com/Office365/Enterprise/about-office-365-identity) 」および「[ハイブリッド id と office 365 のディレクトリ同期](https://docs.microsoft.com/Office365/Enterprise/plan-for-directory-synchronization)」を参照してください。

### <a name="enable-modern-authentication-in-office-365"></a>Office 365 で先進認証を有効にする

Exchange Online の先進認証を有効にするには、「 [Exchange online で先進認証を有効](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)にする」を参照してください。 Skype for Business Online を使用している場合は、Skype for Business Online の先進認証が有効になっていることも確認してください。 詳細については、「 [Skype For Business Online: 先進認証のためにテナントを有効](https://aka.ms/SkypeModernAuth)にする」を参照してください。

Microsoft Teams の会議の設定がオンになっていて、かつ基本認証を使用するように構成されているデバイスがないことを確認する前に、Exchange Online の基本認証ポリシーを削除したり、テナントの基本認証を無効にしたりすることをお勧めします。

Exchange Online で基本認証を無効にする方法の詳細については、「 [Exchange online で基本認証を無効にする](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)」を参照してください。

## <a name="hybrid-modern-authentication"></a>ハイブリッド先進認証

オンプレミスの Exchange server や Skype for Business server への認証を成功させるには、Microsoft Teams のルームで使用されているリソースアカウントが、Azure AD から承認を取得するように構成されていることを確認する必要があります。 組織に適したハイブリッド id とメソッドの詳細については、次のトピックを参照してください。 

- [パスワードのハッシュの同期とは](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-phs)
- [パススルー認証とは何ですか?](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta)
- [フェデレーションとは](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-fed)

### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>Microsoft Teams のルームに固有の前提条件

ハイブリッドトポロジでの先進認証を有効にするための前提条件は、[ハイブリッド先進認証の概要と、オンプレミスの Skype For business および Exchange server で使用するための前提条件](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview)に含まれています。 この記事で説明されているすべての前提条件が適用されます。

ただし、Microsoft Teams の会議室は、[リソース所有者のパスワード](https://tools.ietf.org/html/rfc6749#section-1.3.3)認証と先進認証用の下位の REST api を使用しているため、次の重要な相違点は Microsoft Teams のルームに固有のものであるという点に注意してください。

- Exchange server 2016 CU8 以降、または Exchange Server 2019 CU1 以降がインストールされている必要があります。
- Skype for Business Server 2015 CU5 以降以降、または Skype for Business Server 2019 以降がインストールされている必要があります。
- 使用しているトポロジに関係なく MFA はサポートされません。
- Azure AD でサポートされているサードパーティ認証プロバイダーを使用している場合は、OAuth をサポートし、リソース所有者のパスワード認証を使用する必要があります。
- アプリケーションで構成されているリソースアカウントに対して、デバイスレベルの条件付きアクセスポリシーは使用しないでください。 この操作を行うと、サインインエラーが発生します。 代わりに、[ここ](https://techcommunity.microsoft.com/t5/intune-customer-success/bg-p/IntuneCustomerSuccess)で説明したガイダンスを使用して、Microsoft Intune にデバイスを登録して、コンプライアンスポリシーを適用します。

### <a name="configure-exchange-server"></a>Exchange Server の構成

Exchange Server でハイブリッド先進認証を有効にするには、「[オンプレミスの Exchange Server でハイブリッド先進認証を使用するように構成する方法](https://docs.microsoft.com/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)」を参照してください。

### <a name="configure-skype-for-business-server"></a>Skype for Business Server を構成する

Skype for Business Server とのハイブリッド先進認証を有効にするには、「[ハイブリッド先進認証を使用するように skype For business をオンプレミスで構成する方法](https://docs.microsoft.com/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)」を参照してください。

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>Skype for Business および Exchange を削除または無効にする

セットアップでハイブリッド先進認証が許可されていない場合、または Exchange または Skype for Business のハイブリッド先進認証を削除または無効にする必要がある場合は、「 [Skype For business および exchange からのハイブリッド先進認証の削除または無効化](https://docs.microsoft.com/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha)」を参照してください。

### <a name="azure-ad-conditional-access"></a>Azure AD の条件付きアクセス

Microsoft Teams のルームで使用されるリソースアカウントを、IP/場所ベースのアクセスに対して構成することができます。 詳細については、「[条件付きアクセス: 場所でのアクセスをブロック](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-location)する」を参照してください。

その他の条件付きアクセスポリシーはサポートされません。 デバイスのコンプライアンスの詳細については、[こちら](https://techcommunity.microsoft.com/t5/intune-customer-success/bg-p/IntuneCustomerSuccess)のガイダンスを参照してください。  
