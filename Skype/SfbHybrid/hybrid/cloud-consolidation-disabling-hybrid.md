---
title: ハイブリッドを無効にしてクラウドへの移行を完了する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: この付録には、Teams と Skype for Business のクラウド統合の一部としてハイブリッドを無効にするための詳細な手順が含まれています。
ms.openlocfilehash: c6d042095298f6cab8d9474a521b9362ece13e0d
ms.sourcegitcommit: 0dda90122769385529f78f70b0467848da97e5ec
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2020
ms.locfileid: "44173973"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a>ハイブリッドを無効にしてクラウドへの移行を完了する

すべてのユーザーをオンプレミスからクラウドに移行した後は、オンプレミスの Skype for Business の配置を使用停止にすることができます。 ハードウェアを削除する以外に、重要なステップとして、ハイブリッドを無効にすることによってオンプレミスの配置を Office 365 から論理的に分離します。 ハイブリッドの無効化は、3つの手順で構成されます。

- Office 365 を指すようにドメインの DNS レコードを更新する。
- Office 365 組織の分割ドメインを無効にします。
- オンプレミスの Office 365 との通信機能を無効にします。

これらの手順は、1つの単位として一緒に実行する必要があります。 詳細については、以下を参照してください。 また、オンプレミスの展開が切断されると、移行されたユーザーの電話番号を管理するためのガイドラインが提供されます。

> [!Important] 
>Azure ad Connect into Azure AD を使用して、Active Directory 同期の msRTCSIP 属性を引き続き使用する必要があります。  サポートからの指示がない限り、これらの属性はクリアしないでください。  オンプレミス環境では、Disable-CsUser を実行しないでください。 ユーザーの SIP アドレスを変更する必要がある場合は、オンプレミスの Active Directory でこれを実行し、以下に説明するように Azure AD Connect を使用して azure AD にこの変更を同期させます。 同様に、電話番号を変更する必要があり、ユーザーの LineURI が既にオンプレミスで定義されている場合は、オンプレミスの Active Directory でこれを変更する必要があります。
>オンプレミスから移行した後でオンプレミスの msRTCSIP 属性をオフにすると、ユーザーのサービスが失われる可能性があります。



1.  *Office 365 を指すように DNS を更新します。*
社内組織の既存の外部 DNS レコードを更新して、Skype for Business レコードがオンプレミス展開ではなく Office 365 をポイントできるようにする必要があります。 具体的には次のとおりです。

    |レコードの種類|名前|TTL|値|用途|
    |---|---|---|---|---|
    |SRV|_sipfederationtls _tcp|3600|100 1 5061 sipfed。<span>com|フェデレーションを有効にする|
    |SRV|_sip _tls|3600|100 1 443 sipdir。<span>com|Skype for Business ユーザーにとって必須|
    |CNAME| lyncdiscover|   3600|   webdir。<span>com|Skype for Business ユーザーにとって必須|
    |CNAME| sip|    3600|   sipdir。<span>com|以前の従来の SIP 電話にのみ必要|

    また、会議またはダイヤルイン (存在する場合) の CNAME レコードを削除することもできます。

    > [!Note] 
    > まれなケースとして、組織の 365 DNS を変更することによって、他の組織がフェデレーションの構成を更新するまで、他の組織とのフェデレーションを停止させることがあります。
    >
    > - 以前の直接フェデレーションモデル (許可されたパートナーサーバーとも呼ばれる) を使用しているフェデレーション組織は、組織がプロキシ FQDN を削除するために許可されているドメインエントリを更新する必要があります。 この従来のフェデレーションモデルは DNS SRV レコードに基づくものではないため、組織がクラウドに移行すると、このような構成は古くなります。
    > 
    > - Sipfed のホスティングプロバイダーが有効になっていないフェデレーション組織。<span>com は、を有効にするために、構成を更新する必要があります。 このような状況は、フェデレーション組織が純粋にオンプレミスにあり、ハイブリッドまたはオンラインのテナントと共にフェデレーションが行われていない場合にのみ可能です。 このような場合、これらの組織とのフェデレーションは、ホスティングプロバイダーを有効にするまでは機能しません。
    >
    > フェデレーションパートナーのいずれかが直接フェデレーションを使用しているか、またはオンラインまたはハイブリッド組織とフェデレーションされていない可能性がある場合は、クラウドへの移行を完了するための準備として、これに関する連絡をお勧めします。

2.  *Office 365 組織の共有 SIP アドレススペースを無効にします。*
次のコマンドは、Skype for Business Online PowerShell ウィンドウから実行する必要があります。

    ```PowerShell
    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
    ```
 
3.  *オンプレミスの Office 365 との通信機能を無効にします。*  
次のコマンドは、オンプレミスの PowerShell ウィンドウから実行する必要があります。

    ```PowerShell
    Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
    ```

### <a name="manage-sip-addresses-and-phone-numbers-for-users-who-were-migrated-from-on-premises"></a>オンプレミスから移行されたユーザーの sip アドレスと電話番号を管理する

管理者は、オンプレミスの展開を使用停止にした後であっても、オンプレミスの Skype for Business Server からクラウドに移動されたユーザーを管理できます。 ユーザーの SIP アドレスまたはユーザーの回線 URI を変更する場合 (かつ、オンプレミスの Active Directory で SIP アドレスまたは回線 URI が既に定義されている場合) は、オンプレミスの Active Directory でこれを実行して、その値を Azure AD に流す必要があります。 これには、オンプレミスの Skype for Business Server は必要ありません。 代わりに、これらの属性は、Active Directory ユーザーとコンピューター MMC スナップインを使用するか、PowerShell を使用して、社内の Active Directory で直接変更できます。 MMC スナップインを使用している場合は、ユーザーの [プロパティ] ページを開き、[属性エディター] タブをクリックして、変更する適切な属性を検索します。

- ユーザーの SIP アドレスを変更するには、 `msRTCSIP-PrimaryUserAddress`を変更します。 さらに、 `ProxyAddresses`属性に sip 値が含まれている場合は、その sip 値を新しい値`msRTCSIP-PrimaryUserAddress`と一致するように更新します。 SIP の値が含まれていない場合は、空白のままにしておくことができます。

- ユーザーの電話番号を変更するには`msRTCSIP-Line` 、*既に値がある場合*に変更します。

  ![Active Directory ユーザーとコンピューターツール](../media/disable-hybrid-1.png)
  
移行前に、ユーザーがオンプレミスの`LineURI`値を持っていなかった場合は、Skype For Business Online PowerShell モジュール`onpremLineUri`で-パラメーターを使用して[、-パラメーター](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps)を使用して lineuri を変更できます。


## <a name="see-also"></a>関連項目

[Teams と Skype for Business のクラウド統合](cloud-consolidation.md)
