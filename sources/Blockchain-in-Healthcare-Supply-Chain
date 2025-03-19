module Healthcare::SupplyChain {

    use aptos_framework::signer;
    use aptos_framework::coin;
    use aptos_framework::aptos_coin::AptosCoin;

    struct MedicalSupply has store, key {
        delivered: bool,
        verified: bool,
    }

    public fun create_supply(owner: &signer) {
        let supply = MedicalSupply {
            delivered: false,
            verified: false,
        };
        move_to(owner, supply);
    }

    public fun update_supply_status(supply_owner: address, delivered: bool, verified: bool) acquires MedicalSupply {
        let supply = borrow_global_mut<MedicalSupply>(supply_owner);
        supply.delivered = delivered;
        supply.verified = verified;
    }
}
