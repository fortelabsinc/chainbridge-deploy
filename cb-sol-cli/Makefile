SOL_URL=https://github.com/fortelabsinc/chainbridge-solidity
SOL_VERSION="main"
#SOL_BRANCH="forte_bridge"

fetch-contracts:
	@echo " > \033[32mFetching chainbridge-solidity contracts... \033[0m "
	git clone ${SOL_URL} && cd chainbridge-solidity && git checkout ${SOL_VERSION}

compile:
	cd chainbridge-solidity && npm install && npx truffle compile && ./scripts/create_bindings.sh

install: clean fetch-contracts compile
	@echo " > \033[32mInstalling cb-sol-cli... \033[0m "
	npm link .

clean:
	rm -rf chainbridge-solidity/