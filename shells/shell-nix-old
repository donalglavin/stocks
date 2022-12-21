{pkgs ? import <nixpkgs> {} }:

with pkgs;
let
  ibapi = python39.pkgs.buildPythonPackage rec {
    pname = "ibapi";
    version = "9.81.1";

    src = python39.pkgs.fetchPypi {
      inherit pname version;
      sha256 = "";
    };

    doCheck = false;

    meta = {
      homepage = "https://pypi.org/project/ibapi/";
      description = "Interactive Brokers Api";
    };
  };

in
pkgs.mkShell {
  buildInputs = [
    (pkgs.python3.withPackages (ps: [ ps.numpy ps.pandas ps.python-lsp-server ibapi ps.requests]))
  ];
}
