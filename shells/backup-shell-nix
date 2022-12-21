{ pkgs ? import <nixpkgs> {}}:
let
  ibapi = pkgs.pythonPackages.buildPythonPackage rec {
    name = "ibapi";
    version = "1020.01";
    src = pkgs.fetchurl{
      url = "https://interactivebrokers.github.io/downloads/twsapi_macunix.${version}.zip";
      sha256 = "";
    };
    meta = {
      homepage = "https://interactivebrokers.github.io/#";
      description = "Interactive Brokers Official API";
    };
  };
in
pkgs.mkShell {
  buildInputs = [
    (pkgs.python3.withPackages (ps: with ps; [ numpy pandas python-lsp-server ibapi requests]))
    pkgs.emacs
  ];
}


  # Documentation can be found here:
  # https://interactivebrokers.github.io/tws-api/introduction.html
