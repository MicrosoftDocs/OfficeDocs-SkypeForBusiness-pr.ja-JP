---
title: エッジ証明書の更新
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
description: この付録には、Teams および Skype for Business のクラウド統合の一環としてエッジ証明書を更新するための詳細な手順が含まれています。
ms.openlocfilehash: c4339eec5fa303429fdf8f42a7273c8f20f94e5b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762855"
---
# <a name="update-the-edge-certificate"></a>エッジ証明書の更新

エッジ証明書の更新は、SipDomain1 を使用するオンプレミス環境が SipDomain2 を使用してクラウド環境に参加できるようにし、2つの SIP ドメイン間で共有アドレススペース環境で適切にルーティングできるようにするための重要な手順です。 この手順を実行する必要がある状況については、「 [Teams と Skype For business の](cloud-consolidation.md)手順14」を参照してください。 この例では、SipDomain1 は AcquiredCompany です。<span>Com と SipDomain2 は originalcompany です。<span>com。

オンプレミス環境にあるすべてのエッジサーバー上の証明書のサブジェクト代替名 (SAN) を更新して、純粋なオンラインテナントに存在するすべての SIP ドメインを含める必要が<span>あります (任意の onmicrosoft を除く)。com ドメイン)、"sip" という形式です。\<ドメイン> "。  この例では、これは sip です。OriginalCompany。<span>com。 この手順は、ユーザーをクラウドに移行する前に実行することが重要です。

**行う**

1.  「SIP」という形式で、クラウド環境 (* onmicrosoft.com ドメインを除く) のすべての SIP ドメインについて、既存のすべてのエントリと SAN の追加エントリに加えて、新しい外部エッジ証明書を取得します。<DomainName>"です。
2.  各エッジサーバーにローカルに証明書をインストールし、各エッジサービスの Skype エッジサービスに割り当てます。  詳細な手順については、「 [Deploy Edge Service In Skype For Business Server 2015](https://technet.microsoft.com/library/dn951368.aspx)」の「外部エッジインターフェイスの証明書」を参照してください。
3.  各エッジサーバーでエッジサービスを再起動します。 これは、次の PowerShell コマンドを使用して1つのボックスに対して行うことができます。

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a>関連項目

[Teams と Skype for Business のクラウド統合](cloud-consolidation.md)
