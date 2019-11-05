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
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: この付録には、Teams と Skype for Business のクラウド統合の一部としてハイブリッドを無効にするための詳細な手順が含まれています。
ms.openlocfilehash: d441d9fcc5e4f2cec495efabdbea423eaaec882c
ms.sourcegitcommit: 7920c47eb73e665dad4bf7214b28541d357bce25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2019
ms.locfileid: "37962057"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a>ハイブリッドを無効にしてクラウドへの移行を完了する

オンプレミスのすべてのユーザーをクラウドに移行した後、オンプレミスの Skype for Business の展開を使用停止にすることができます。 ハードウェアを削除することに加えて、ハイブリッドを無効にすることによって、オンプレミスの展開を Office 365 から論理的に分離することが重要な手順です。 ハイブリッドの無効化は、3つの手順で構成されます。

1. Office 365 をポイントするように DNS レコードを更新します。

2. Office 365 テナントの分割ドメインを無効にします。

3. オンプレミスの Office 365 との通信機能を無効にします。

これらの手順は、1つの単位として一緒に実行する必要があります。 詳細については、以下を参照してください。 また、オンプレミスの展開が切断されると、移行されたユーザーの電話番号を管理するためのガイドラインが提供されます。

> [!Note] 
> まれなケースとして、組織の 365 DNS を変更することによって、他の組織がフェデレーションの構成を更新するまで、他の組織とのフェデレーションを停止させることがあります。<ul><li>
以前の直接フェデレーションモデル (許可されたパートナーサーバーとも呼ばれる) を使用しているフェデレーション組織は、組織がプロキシ FQDN を削除するために許可されているドメインエントリを更新する必要があります。 この従来のフェデレーションモデルは DNS SRV レコードに基づくものではないため、組織がクラウドに移行すると、このような構成は古くなります。 </li><li>Sipfed のホスティングプロバイダーが有効になっていないフェデレーション組織。<span>com は、を有効にするために、構成を更新する必要があります。 この状況は、フェデレーション組織が純粋にオンプレミスにあり、ハイブリッドまたはオンラインテナントとのフェデレーションが行われていない場合にのみ可能です。 このような場合、これらの組織とのフェデレーションは、ホスティングプロバイダーを有効にするまでは機能しません。</li></ul>フェデレーションパートナーのいずれかが直接フェデレーションを使用しているか、またはすべてのオンラインまたはハイブリッド組織とフェデレーションされている可能性がある場合は、クラウドへの移行を完了するための準備として、これに関する連絡をお勧めします。

1.  *Office 365 を指すように DNS を更新します。*
社内の組織の外部 DNS を更新して、Skype for Business レコードがオンプレミスの展開ではなく Office 365 をポイントできるようにする必要があります。 具体的には次のとおりです。

    |レコードの種類|名前|TTL|Value|
    |---|---|---|---|
    |SRV|_sipfederationtls._tcp|3600|100 1 5061 sipfed。<span>com|
    |SRV|(sip) tls|3600|100 1 443 sipdir。<span>com|
    |CNAME| lyncdiscover|   3600|   webdir。<span>com|
    |CNAME| sip|    3600|   sipdir。<span>com|
    |CNAME| 満たせ|   3600|   webdir。<span>com|
    |CNAME| deny  |3600|  webdir。<span>com|

2.  *Office 365 テナントの共有 SIP アドレススペースを無効にします。*
次のコマンドは、Skype for Business Online PowerShell ウィンドウから実行する必要があります。

    ```
    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
    ```
 
3.  *オンプレミスで Office 365 と通信する機能を無効にします。*  
次のコマンドは、オンプレミスの PowerShell ウィンドウから実行する必要があります。  以前に Skype for Business Online セッションをインポートしたことがある場合は、次のように、新しい Skype for Business PowerShell セッションを開始します。

```
    Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
```

### <a name="manage-phone-numbers-for-users-who-were-migrated-from-on-premises"></a>オンプレミスから移行されたユーザーの電話番号を管理する

管理者は、オンプレミスの展開を使用停止にした後であっても、オンプレミスの Skype for Business Server からクラウドに移動されたユーザーを管理できます。 2つの異なる可能性があります。

- ユーザーは、移動前に、オンプレミスの lineURI の値を持っていませんでした。 

  この場合は、Skype for Business Online Powershell[モジュールの-](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) onpremLineUri パラメーターを使用して、lineuri を変更することができます。

- ユーザーは、移動前に、オンプレミスの lineURI を使用しました (ユーザーがエンタープライズ Voip を有効にしているため)。 

  LineURI を変更する場合は、オンプレミスの Active Directory でこれを実行し、その値が Azure AD に流れるようにする必要があります。 これには、オンプレミスの Skype for Business Server は必要ありません。 代わりに、この属性 msRTCSIP は、Active Directory ユーザーとコンピューター MMC スナップインを使用するか、PowerShell を使用して、オンプレミスの Active Directory で直接編集することができます。 MMC スナップインを使用している場合は、ユーザーの [プロパティ] ページを開き、[属性エディター] タブをクリックして、msRTCSIP 行を検索します。

  ![Active Directory ユーザーとコンピューターツール](../media/disable-hybrid-1.png)

## <a name="see-also"></a>関連項目

[Teams と Skype for Business のクラウド統合](cloud-consolidation.md)
