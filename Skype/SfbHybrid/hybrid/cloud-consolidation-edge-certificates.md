---
title: エッジ証明書を更新する
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
description: この付録には、Teams および Skype for Business のクラウド統合の一環としてエッジ証明書を更新するための詳細な手順が含まれています。
ms.openlocfilehash: 1c3aaa8859db530ceccbebc68ae76f21e8d4a77f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160651"
---
# <a name="update-the-edge-certificate"></a>エッジ証明書を更新する

エッジ証明書の更新は、SipDomain1 を使用するオンプレミス環境が SipDomain2 を使用してクラウド環境に参加できるようにし、2つの SIP ドメイン間で共有アドレススペース環境で適切にルーティングできるようにするための重要な手順です。 この手順を実行する必要がある状況については、「 [Teams と Skype For business の](cloud-consolidation.md)手順14」を参照してください。 この例では、SipDomain1 は AcquiredCompany です。<span>Com と SipDomain2 は originalcompany です。<span>com。

オンプレミス環境にあるすべてのエッジサーバー上の証明書のサブジェクト代替名 (SAN) を更新して、純粋なオンラインテナントに存在するすべての SIP ドメインを含める必要が<span>あります (任意の onmicrosoft を除く)。com ドメイン)、"sip" という形式です。\<ドメイン> "。  この例では、これは sip です。OriginalCompany。<span>com。 この手順は、ユーザーをクラウドに移行する前に実行することが重要です。

**手順:**

1.  「SIP」という形式で、クラウド環境 (* onmicrosoft.com ドメインを除く) のすべての SIP ドメインについて、既存のすべてのエントリと SAN の追加エントリに加えて、新しい外部エッジ証明書を取得します。<DomainName>"です。
2.  各エッジサーバーにローカルに証明書をインストールし、各エッジサービスの Skype エッジサービスに割り当てます。  詳細な手順については、「 [Deploy Edge Service In Skype For Business Server 2015](https://technet.microsoft.com/en-us/library/dn951368.aspx)」の「外部エッジインターフェイスの証明書」を参照してください。
3.  各エッジサーバーでエッジサービスを再起動します。 これは、次の PowerShell コマンドを使用して1つのボックスに対して行うことができます。

    ```
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a>関連項目

[Teams と Skype for Business のクラウド統合](cloud-consolidation.md)