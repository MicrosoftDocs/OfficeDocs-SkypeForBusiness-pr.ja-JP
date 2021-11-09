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
ms.localizationpriority: medium
description: この付録には、クラウド統合の一環としてエッジ証明書を更新する手順の詳細TeamsおよびSkype for Business。
ms.openlocfilehash: bb8d2eabf17d83546737d3d94fb4add5dc0a892e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857114"
---
# <a name="update-the-edge-certificate"></a>エッジ証明書の更新

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


エッジ証明書の更新は、SipDomain1 を使用したプレム環境が SipDomain2 を使用してクラウド環境に参加し、2 つの SIP ドメイン間で共有アドレス空間環境で適切なルーティングを行う重要なステップです。 この手順を実行する可能性があるコンテキストについては[、Teams](cloud-consolidation.md)およびSkype for Businessクラウド統合の手順 14 を参照してください。 この例では、SipDomain1 は AcquiredCompany です。 <span>com と SipDomain2 は OriginalCompany です。 <span>com.

オンプレミス環境内のすべてのエッジ サーバー上の証明書のサブジェクト代替名 (SAN) を更新して、純粋なオンライン テナントに存在するすべての SIP ドメイン (onmicrosoft <span> を除く) を含める必要があります。com ドメイン) の形式で "sip. \<domain> ".  この例では、これは sip です。OriginalCompany。 <span>com. この手順は、ユーザーをクラウドに移行する前に実行する必要があります。

**手順:**

1.  フォーム内のすべての既存のエントリと、クラウド環境内のすべての SIP ドメイン (*.onmicrosoft.com ドメインを除く) の SAN 内の追加エントリを持つエッジの新しい外部エッジ証明書を取得します。 `sip.<DomainName>`
2.  証明書を各エッジ サーバーにローカルにインストールし、各エッジ サービスSkypeエッジ サービスに割り当てる。  詳細な手順については、「Deploy Edge Service in the [2015」](../../SfbServer/deploy/deploy-edge-server/deploy-edge-servers.md)の「外部エッジ インターフェイス証明書」を参照Skype for Business Serverしてください。
3.  各エッジ サーバーでエッジ サービスを再起動します。 これは、次の PowerShell コマンドを使用して 1 つのボックスに対して実行できます。

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a>関連項目

[クラウドの統合 :TeamsとSkype for Business](cloud-consolidation.md)